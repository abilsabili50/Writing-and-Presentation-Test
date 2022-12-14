# **Writing and Presentation Test Week 6**

## List Materi :

1. [MySQL Basic](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-6#mysql-basic)
2. [MySQL Lanjutan](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-6#mysql-lanjutan)
3. [Express Authentication & Authorization](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-6#express-authentication--authorization)
4. [Sequelize](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-6#sequelize)

## MySQL Basic

1.  ### Database

    Database adalah sekumpulan data yang disimpan dan dikelola sedemikian rupa berdasarkan ketentuan tertentu sehingga mudah dalam pengelolaannya. Agar dapat mengelola sebuah database diperlukan sebuah DBMS (Database Management System). Salah satu contoh DBMS adalah MySQL. MySQL merupakan sebuah open source software untuk mengelola relational database yang berbasis SQL.

2.  ### Relational Database

    Relational database adalah sekumpulan informasi yang dapat dikelola dan memiliki hubungan antar data satu dengan data lainnya sesuai dengan yang telah ditentukan sebelumnya.

3.  ### MySQL Tipe Data

    1. Number
       Data yang berisikan kumpulan karakter angka.
    2. String
       Data yang berisikan kumpulan karakter termasuk karakter simbol.
    3. Boolean
       Data yang berisikan 2 value yaitu `true` dan `false`.
    4. Date
       Data yang berisikan tanggal dengan format `dd-mm-yyyy`.
    5. Time
       Data yang berisikan waktu dengan format `HH:MM:SS`.
    6. Null
       Data yang merepresentasikan bahwa sebuah nilai belum diassign.

4.  ### Query Sederhana

    #### DDL (Data Definition Language)

    Query yang biasa digunakan dalam melakukan DDL antara lain:

    1. Membuat Tabel

       ```sql
       create table person(
          nik int primary key not null auto_increment,
          nama varchar(50)
       );
       ```

    2. Mengubah Struktur Tabel

       ```sql
       alter table person add alamat varchar(255);
       ```

    3. Menghapus Database / Table

       ```sql
       drop database person;
       ```

    #### DML (Data Manipulation Language)

    Query yang biasa digunakan dalam memanipulasi data antara lain:

    1. Menampilkan Data

       ```sql
       select * from person;
       ```

    2. Menambahkan Data

       ```sql
       insert into person ('nik', 'nama', 'alamat') values ('1234', 'Abil', 'Balongsari');
       ```

    3. Mengubah Data

       ```sql
       update person set nik='1235', nama='Abilsabili', alamat='Balongsari Tandes' where nik='1234';
       ```

    4. Menghapus Data

       ```sql
       delete from person where nik='1235';
       ```

## MySQL Lanjutan

1. ### Query Tingkat Lanjut

   1. Menampilkan Data menggunakan Inner Join

      ```sql
      select * from buku inner join penerbit on buku.penerbit = penerbit.id;
      ```

   2. Menampilkan Data menggunakan Left Join

      ```sql
      select * from buku left join penerbit on buku.penerbit = penerbit.id;
      ```

   3. Menampilkan Data Menggunakan Right Join

      ```sql
      select * from buku right join penerbit on buku.penerbit = penerbit.id;
      ```

   4. Menggunakan Aggregate Function (MIN)

      Akan mengembalikan nilai terkecil dari suatu kolom tertentu.

      ```sql
      select min(price) from buku;
      ```

   5. Menggunakan Aggregate Function (MAX)

      Akan mengembalikan nilai terbesar dari suatu kolom tertentu.

      ```sql
      select max(price) from buku;
      ```

   6. Menggunakan Aggregate Function (SUM)

      Akan mengembalikan jumlah total dari suatu kolom tertentu yang bertipe data numerik.

      ```sql
      select sum(price) from buku;
      ```

   7. Menggunakan Aggregate Function (COUNT)

      Akan mengembalikan jumlah record dari suatu kolom tertentu.

      ```sql
      select count(*) from buku;
      ```

   8. Menggunakan Aggregate Function (AVG)

      Akan mengembalikan rata-rata dari suatu kolom tertentu yang bertipe data numerik.

      ```sql
      select avg(price) from buku;
      ```

   9. Menggunakan Aggregate Function (CONCAT)

      Akan mengembalikan hasil concatenasi dari suatu kolom tertentu.

      ```sql
      select concat(first_name, " ", last_name) from person;
      ```

2. ### Query untuk Membuat Relasi Antar Tabel

   Database memiliki beberapa macam relasi, antara lain :

   1. One-to-Many
      Satu baris tabel dapat memiliki hubungan dengan beberapa baris di tabel lainnya.
   2. Many-to-Many
      Digunakan jika satu tabel dengan tabel lainnya memiliki banyak hubungan di setiap baris tabelnya.
   3. One-to-One
      Digunakan jika satu tabel dengan tabel lainnya memiliki hubungan hanya satu di setiap baris tabelnya.

   Untuk dapat membuat relasi antar tabel dapat menggunakan keyword `references`. Berikut contohnya :

   ```sql
    create table mahasiswa (
      nik int primary key not null auto_increment,
      nama varchar(50),
      id_jurusan int,
      foreign key (id_jurusan) references jurusan(id)
    );
   ```

## Express Authentication & Authorization

1. ### Authentication vs Authorization vs Encryption

   - Authentication
     Authentication adalah sebuah sistem verifikasi apakah kita terdaftar didalam suatu aplikasi atau tidak.
   - Authorization
     Authorization adalah sebuah sistem verifikasi yang memverifikasi apa saja yang bisa saya lakukan pada suatu aplikasi.
   - Encryption
     Encryption adalah sebuah sistem transformasi data yang menjadikan data tersebut tidak dapat dibaca kecuali kita memiliki kunci yang benar.

2. ### Variasi Authentication

   - Single-Factor Authentication
     Merupakan sistem autentikasi sederhana yang hanya menggunakan salah satu tipe autentikasi saja, seperti username / password (knowledge-base)
   - Multi-Factor Authentication
     Merupakan sistem autentikasi yang menggunakan paling tidak 2 tipe autentikasi, seperti menggunakan username / password dan OTP.

3. ### Membuat Authentication & Authorization Sederhana

   ```js
   const express = require("express");
   const jwt = require("jsonwebtoken");

   const app = express();

   const user = {
   	id: 1,
   	email: "abil@gmail.com",
   	password: "surabaya",
   	role: "admin",
   	accessToken: null,
   };

   const SECRET_KEY = "halohalohalohalhoalhalaoalahla";

   app.use(express.json());

   // proses autentikasi

   app.get("/login", (req, res) => {
   	const { email, password } = req.body;

   	if (!email || !password)
   		return res
   			.status(400)
   			.send({ status: "fail", msg: "email or password cannot be empty" });

   	if (email != user.email)
   		return res.status(404).send({ status: "fail", msg: "email not found" });

   	if (password != user.password)
   		return res
   			.status(400)
   			.send({ status: "fail", msg: "password incorrect" });

   	const token = jwt.sign({ email, password, role }, SECRET_KEY, {
   		expiresIn: "24h",
   	});

   	res.send({ status: "success", msg: "token has been created", token });
   });

   // proses authorization
   // role = admin
   app.use((req, res, next) => {
   	const token = req.headers["x-access-token"];

   	if (!token)
   		return res.status(403).send({ status: "fail", msg: "forbidden" });

   	const decoded = jwt.verify(token, SECRET_KEY);

   	const { role } = decoded;

   	if (role != "admin")
   		return res.status(403).send({ status: "fail", msg: "forbidden" });

   	next();
   });

   app.get("/admin", (req, res) => {
   	res.send({ status: "success", msg: "you are an admin" });
   });
   ```

## Sequelize

1. ### Penggunaan Sequelize ORM

   - Install Sequelize CLI

     ```bash
     npm install -g sequelize-cli
     ```

   - Install Driver

     ```bash
     npm i --save sequelize mysql
     ```

   - Inisialisasi Project

     ```bash
     npx sequelize-cli init
     ```

   - Setting Database (dalam folder `config`)

     ```js
     const Sequelize = require("sequelize");

     const sequelize = new Sequelize({
     	host: "localhost",
     	dialect: "mysql",
     	database: "todoApp",
     	username: "root",
     	password: "",
     });
     ```

   - Generate Model

     ```bash
     npx sequelize-cli model:generate --name Todo --attributes title:string, status:string
     ```

   - Migrate Model

     ```bash
     npx sequelize-cli db:migrate
     ```

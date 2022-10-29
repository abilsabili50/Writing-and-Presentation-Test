# **Writing and Presentation Test Week 5**

## List Materi :

1. [Web Server](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#web-server)
2. [RESTFul Api](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#restful-api)
3. [NodeJs](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#nodejs)
4. [ExpressJs](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#expressjs)
5. [Design Database](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#design-database) - going to be added

## Web Server

Web server terdiri dari 2 sisi, antara lain :

1. Hardware Side

   Berdasarkan sisi hardware, web server adalah sebuah perangkat yang menyimpan software dari web server dan komponen-komponen dari website yang disimpan pada web server seperti file html, image, dan lain-lain.

2. Software Side

   Berdasarkan sisi software, web server meliputi beberapa bagian yang mengatur bagaimana client mengakses sebuah file yang telah dihosting.

Web server terdiri dari 2 macam antara lain :

1. Static Web Server

   Dinamakan `static` karena server akan mengirim konten secara apa adanya sesuai yang diminta oleh client.

2. Dynamic Web Server

   Dinamakan `dynamic` karena server akan mengatur isi konten terlebih dahulu pada sisi server sebelum mengirimkannya ke sisi client. Biasanya didalamnya meliputi `database`.

## RESTFul Api

### REST (Representational State Transfer)

Rest merupakan gaya arsitektur dalam penyediaan standar antar sistem komputer di web, sehingga memudahkan dalam berkomunikasi satu sama lain.

### RESTFul

Sebuah sistem yang menggunakan arsitektur dari `REST` sering disebut `RESTFul`. RESTFul bersifat stateless dan memisahkan antara client-side dan server-side. Pada gaya arsitektur ini biasanya development dapat dilakukan secara independen baik client-side maupun server-side tanpa mengetahui satu sama lain.

Dalam menggunakan REST interface, client-side yang berbeda dapat menggunakan endpoint, melakukan actions, dan mendapatkan response yang sama. Client-side dapat berupa web, mobile, ataupun desktop platform.

REST menuntut agar client membuat permintaan dalam berinteraksi. Dalam permintaan tersebut biasanya terdapat beberapa komponen, antara lain :

1.  HTTP Verbs (`GET`, `POST`, `PUT`, `DELETE`)
2.  Header, untuk memberikan informasi tambahan.
3.  Path / endpoint
4.  Pesan body (`optional`)

## NodeJs

NodeJs merupakan sebuah runtime javascript yang dibuat menggunakan V8 engine pada Chrome yang memungkinkan kita dapat mengeksekusi kode javascript tanpa menggunakan file HTML (local execution). Hal ini membuat NodeJs dapat menjadi pertimbangan jika ingin membuat aplikasi `backend`. NodeJs juga memiliki open source package ekosistem (NPM) yang menjadi package ekosistem terbesar di dunia.

### Instalasi

Untuk menginstall-nya klik [**disini**](https://nodejs.org/en/download/)

### Node REPL (Read Eval Print Loop)

Node REPL merupakan embedded fitur dari node yang memungkinkan kita dapat mengeksekusi script javascript secara langsung. Untuk menggunakan fitur ini dapat gunakan command berikut :

```bash
node
```

Setelah klik `enter` cli akan masuk kedalam mode REPL. Disana kita dapat langsung menuliskan kode javascript.

Berikut contoh penggunaanya.

<img width="431" alt="image" src="https://user-images.githubusercontent.com/73186952/198816235-10dbf2ef-d2e0-42fe-8712-e9c03acf1508.png">

### Program NodeJs

Untuk membuat program nodeJs sederhana perlu dibuat file javascript. Setelah itu, eksekusi kode menggunakan command berikut.

```bash
node <nama_file>

# contoh implementasi
node index.js
```

Berikut contoh hasil program nodeJs sederhana.

![image](https://user-images.githubusercontent.com/73186952/198816451-14802841-18c3-4dfe-bd28-4f2b880b0f70.png)

### Node Modules

Pada nodeJs terdapat 3 kategori module yaitu :

1. Core Modules

   Core modules merupakan modul-modul yang sudah include saat kita install nodejs. Contohnya seperti `fs` (filesystem), `http` (server-side scripting), dan masih banyak lagi.

   Untuk pembuatan server kita dapat menggunakan local module `http`. Berikut implementasinya.

   ```js
   const http = require("http");

   http
   	.createServer((req, res) => {
   		res.write("Halo dunia");
   		res.end();
   	})
   	.listen(3000, "localhost", (err) => {
   		if (err) return console.log(err);

   		console.log("Server running at port 3000");
   	});
   ```

2. Local Modules

   Local module merupakan sebuah module yang kita buat sendiri. Untuk mengimport-nya kita hanya perlu require(`PATH_FILE`).

3. External Modules

   Sedangkan, external module merupakan sebuah module yang dibuat oleh orang lain. Module-module tersebut biasanya terletak pada NPM (Node Package Manager).

## ExpressJs

Express merupakan salah satu eksternal package yang terdapat pada NPM (Node Package Manager). Express dapat digunakan untuk membuat aplikasi backend sederhana. Bahkan, express sering disebut-sebut sebagai framework karena didalam express terdapat template engine yang memungkinkan kita dapat membuat aplikasi berbasis website baik pada sisi frontend dan backend sekaligus.

### Inisialisasi Folder

```bash
npm init --y
```

### Installasi

```bash
npm install express
```

### Penggunaan

```js
const express = require("express");
const app = express();

app.get("/", (req, res) => {
	res.send("Halo Dunia");
});

app.listen(3000, () => {
	console.log("Server running on port 3000");
});
```

### Express Middleware

Middleware adalah sebuah aksi yang dieksekusi sebelum request diterima langsung oleh server. Middleware biasanya digunakan untuk filtering dan security. Contohnya untuk pengecekan user yang sudah login atau belum sebelum user dapat mengakses sebuah sumber. Contoh lainnya pada saat pengecekan user yang ingin mengakses resource yang hanya bisa diakses oleh user dengan role admin.

Pada express, middleware biasanya menggunakan keyword `app.use(middleware)`. Selain itu middleware juga bisa digunakan pada scope routing seperti `app.get("/", middleware, handler)`.

Contoh penggunaannya seperti berikut.

```js
const express = require("express");
const app = express();

// middleware
app.use(express.json());

app.get("/", (req, res) => {
	res.send({
		status: "success",
		msg: "halo dunia",
	});
});

app.listen(3000, () => {
	console.log("Server running on port 3000");
});
```

### Express Routing

Routing digunakan untuk mengatur endpoint yang akan dilakukan request. Dari percobaan sebelumnya, sebenarnya kita sudah implementasi routing menggunakan `app.get("/");`. Namun, express sudah menyediakan method untuk mengatur routes agar route dapat dipisahkan dengan main file. Berikut contoh implementasinya.

```js
const router = require("express").Router();

router.get("/", (req, res) => {
	res.send("halo dunia");
});

router.get("/:nama", (req, res) => {
	res.send(`Halo ${req.params.nama}`);
});

module.exports = router;
```

## Design Database

Database adalah sekumpulan data yang disimpan dan dikelola sedemikian rupa berdasarkan ketentuan tertentu sehingga mudah dalam pengelolaannya.

### Studi Kasus

Membuat desain database dari orang yang menyukai film dengan genre tertentu.

### Langkah Pembuatan Desain Database

1.  #### Menentukan Entity

Pada kasus diatas entity yang terbentuk antara lain

1. Orang
2. Film
3. Genre

Maka didapat desainnya sebagai berikut.

![image](https://user-images.githubusercontent.com/73186952/198849533-5ce91fa7-cca5-4cc4-87ee-39b73f890173.png)

2.  #### Menentukan Atribute dari Entity

Dari entitas-entitas diatas terbentuklah atribut sebagai berikut.

- Orang

  1.  NIK
  2.  nama
  3.  jenis_kelamin

- Film

  1.  id_film
  2.  judul
  3.  tahun_rilis

- Genre

  1.  id_genre
  2.  nama_genre

Maka didapat desainnya sebagai berikut.

![image](https://user-images.githubusercontent.com/73186952/198849548-1def3340-1eba-4566-a9f3-bb154bfed155.png)

3. #### Menentukan Relasi Antar Entity

Dari entitas-entitas diatas terbentuklah relasi sebagai berikut.

1. Orang - Film (`many-to-many`)
2. Film - Genre (`many-to-many`)

Maka didapat ERD sebagai berikut.

![image](https://user-images.githubusercontent.com/73186952/198849741-690b1d71-96ac-4a78-abc7-732489427123.png)

### Hasil Desain Database

Dari langkah-langkah diatas didapatlah desain database seperti berikut.

![image](https://user-images.githubusercontent.com/73186952/198850087-fe6a2238-b174-44c6-9e8e-b3301f95f338.png)

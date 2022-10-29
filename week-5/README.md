# **Writing and Presentation Test Week 5**

## List Materi :

1. [Web Server](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#web-server) - going to be added
2. [RESTFul Api](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#restful-api) - going to be added
3. [NodeJs](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#nodejs) - going to be added
4. [ExpressJs](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#expressjs) - going to be added
5. [Design Database with MySQL](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-5#design-database-with-mysql) - going to be added

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

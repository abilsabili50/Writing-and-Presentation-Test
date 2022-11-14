# **Writing and Presentation Test Week 7**

## List Materi :

1. [Sequelize](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#sequelize)
2. [MongoDB](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#mongodb)
3. [Mongoose](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#mongoose)
4. [Docker](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#docker)

## Sequelize

Setelah generate model dan seedersnya maka kita bisa menggunakan ORM sequelize untuk membuat rest api.

### Build Restful API Using Sequelize

#### Get All Todos

Untuk mendapatkan list todo kita bisa menggunakan method `.findAll()`.

```js
const router = require("express").Router;
const Todos = require("../models"").Todo;

router.get("/", async (req, res) => {
	try {
		const todos = await Todos.findAll();
		res.send({
			status: "success",
			msg: "todos fetched successfully",
			data: todos,
		});
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

module.exports = router;
```

#### Get Todo

Untuk mendapatkan list todo kita bisa menggunakan method `.findOne()`.

```js
const router = require("express").Router;
const Todos = require("../models").Todo;

router.get("/:id", async (req, res) => {
	const { id } = req.params;
	try {
		const todos = await Todos.findOne({ id: Number(id) });
		res.send({
			status: "success",
			msg: "todo fetched successfully",
			data: todos,
		});
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

module.exports = router;
```

#### Add Todo

Untuk mendapatkan list todo kita bisa menggunakan method `.create()`.

```js
const router = require("express").Router;
const Todos = require("../models").Todo;

router.post("/", async (req, res) => {
	const newTodo = req.body;
	try {
		await Todos.create(newTodo);
		res.send({ status: "success", msg: "todo created successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

module.exports = router;
```

#### Update Todo

Untuk mendapatkan list todo kita bisa menggunakan method `.update()`.

```js
const router = require("express").Router;
const Todos = require("../models").Todo;

router.put("/:id", async (req, res) => {
	const { id } = req.params;
	const newTodo = req.body;
	try {
		await Todos.update(newTodo, { where: { id } });
		res.send({ status: "success", msg: "todo updated successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

module.exports = router;
```

#### Delete Todo

Untuk mendapatkan list todo kita bisa menggunakan method `.destroy()`.

```js
const router = require("express").Router;
const Todos = require("../models").Todo;

router.put("/:id", async (req, res) => {
	const { id } = req.params;
	try {
		await Todos.destroy({
			where: {
				id,
			},
		});
		res.send({ status: "success", msg: "todo deleted successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

module.exports = router;
```

## MongoDB

MongoDB adalah salah satu database noSQL yang bersifat open source dan cukup populer digunakan. Jika di SQL kita sering mendengar istilah tabel dan record maka jika di mongoDB kita akan sering mendengar istilah collection sebagai tabel dan dokumen sebagai record. Data yang digunakan pada mongodb memiliki format json sehingga lebih mudah dalam pengoperasiannya. Berikut contoh isi dokumen pada mongoDB (data).

```json
[
	{
		"_id": ObjectId("AAA"),
		"nama": "Abil",
		"email": "abilsabili@gmail.com",
		"password": "abilsabili123"
	},
]
```

### Installasi

Untuk installasi dapat mengunjungi websitenya.
Community - [disini](https://www.mongodb.com/try/download/community) <br>
Tools - [disini](https://www.mongodb.com/try/download/tools)

Jika sudah menginstall semuanya kita dapat menggunakan mongodb menggunakan mongodbCompass (GUI Version) maupun mongosh (cli version).

### Operasi CRUD pada MongoDB

- Buka CMD / Git Bash / Powershell
- Ketik mongosh

  ```bash
  mongosh
  ```

  Maka akan masuk ke tampilan mongo shell
  ![image](https://user-images.githubusercontent.com/73186952/201571817-de84a68b-9503-47ba-9501-296617abcb8d.png)

- Pilih database
  Untuk melihat database yang tersedia ketik command berikut.

  ```bash
  show databases
  ```

  Dan gunakan keyword `use` untuk menggunakan database tersebut.

  ```bash
  use <nama_database>
  ```

- Membuat Collection dan Dokumen

  ```bash
  show collections
  ```

  Jika tidak ada collections, kita dapat membuatnya dengan command berikut.

  ```bash
  db.createCollection("users")
  ```

  Tambah data pada collection tersebut.

  ```bash
  db.users.insertOne({nama: "Abilsabili", email:"abilsabili@gmail.com", password: "surabaya123"})
  ```

- Menampilkan Data

  ```bash
  db.users.find()
  ```

  Output :
  ![image](https://user-images.githubusercontent.com/73186952/201572519-604e9184-6d56-4767-a169-641cbea92b58.png)

- Mengubah Data

  ```bash
  db.users.updateOne({email: "abilsabili@gmail.com"},{$set: {password: "surabaya"}})
  ```

  Output :
  ![image](https://user-images.githubusercontent.com/73186952/201573920-81f21542-2f37-4f8a-8606-3f0185cfda97.png)

- Menghapus Data

  ```bash
  db.users.deleteOne({email: "abilsabili20@gmail.com"})
  ```

  Output :
  ![image](https://user-images.githubusercontent.com/73186952/201574539-1c5f5071-4955-4460-9325-09427e5611aa.png)

### MongoDB Relationship

- One-to-One

  Pada kasus one-to-one relationship biasa digunakan sistem embedding. Contohnya satu user hanya bisa memiliki 1 `_id`.

  ```json
  {
  	"_id": ObjectId("12345"),
  	"name": "Abilsabili",
  	"role": "admin",
  	"email": "abilsabili@gmail.com"
  }
  ```

- One-to-Many

  Pada kasus one-to-many relationship biasa digunakan sistem referencing. Contohnya jika 1 user bisa memiliki banyak pesanan.

  ```json
  "_id": ObjectId("12345"),
  "name": "Abilsabili",
  "pesanan": [ObjectId("AAA"), ObjectId("BBB"), ObjectId("CCC")]
  ```

- Many-to-Many

  Pada kasus many-to-many relationship biasanya juga menggunakan sistem referencing. Contohnya jika seorang user bisa memiliki banyak lagu yang disukai dan sebuah lagu bisa disukai oleh banyak user.

  ```json
  {
  	"_id": ObjectId("123"),
  	"name": "Abil",
  	"liked_song": [
  		ObjectId("AAA"),
  		ObjectId("BBB"),
  		ObjectId("CCC")
  	]
  }

  {
  	"_id": ObjectId("AAA"),
  	"song_name": "Aminlah Bersamaku",
  	"liked_by_user": [
  		ObjectId("123"),
  		ObjectId("124"),
  		ObjectId("125")
  	]
  }
  ```

## Mongoose

### Membuat RESTFul API Dengan Mongoose

```js
const express = require("express");
const app = express();
const mongoose = require("mongoose");

app.use(express.json());

mongoose
	.connect("mongodb://localhost:27017/users")
	.then(() => console.log("database connected"))
	.catch((error) => console.log(error.message));

const Schema = mongoose.Schema;

const users = new Schema({
	name: String,
	email: String,
});

const User = mongoose.model("user", users);

app.get("/", async (req, res) => {
	try {
		const data = await User.find();
		res.send({ status: "success", msg: "all todos found", data });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

app.get("/:id", async (req, res) => {
	const { id } = req.params;

	try {
		const data = await User.findOne({ _id: id });
		res.send({ status: "success", msg: "todo found", data });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

app.post("/", async (req, res) => {
	const { name, email } = req.body;

	try {
		const user = new User({ name, email });
		const data = await user.save();
		res
			.status(201)
			.send({ status: "success", msg: "user created successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

app.put("/:id", async (req, res) => {
	const { id } = req.params;
	try {
		await User.findOneAndUpdate({ _id: id }, { ...req.body });
		res.send({ status: "success", msg: "user updated successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

app.delete("/:id", async (req, res) => {
	const { id } = req.params;
	try {
		await User.deleteOne({ _id: id });
		res.send({ status: "success", msg: "user deleted successfully" });
	} catch (error) {
		res.status(500).send({ status: "fail", msg: error.message });
	}
});

app.listen(3000, () => {
	console.log("server running on http://localhost:3000");
});
```

### Membuat API Specification

#### A. Get All Users

- Method : GET
- Endpoint : `/`
- Header :
  - Accept: application/json
- Response Status Code : `200`
- Response :
  ```json
  {
  	"status": "string",
  	"msg": "string",
  	"data": [
  		{
  			"_id": "ObjectId",
  			"name": "string",
  			"email": "string"
  		}
  	]
  }
  ```

#### B. Get User By Id

- Method : GET
- Endpoint : `/{id}`
- Header :
  - Accept: application/json
- Response Status Code : `200`
- Response :
  ```json
  {
  	"status": "string",
  	"msg": "string",
  	"data": {
  		"_id": "ObjectId",
  		"name": "string",
  		"email": "string"
  	}
  }
  ```

#### C. Add User

- Method : POST
- Endpoint : `/`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :
  ```json
  {
  	"name": "string",
  	"email": "string"
  }
  ```
- Response Status Code : `201`
- Response :
  ```json
  {
  	"status": "string",
  	"msg": "string"
  }
  ```

#### D. Update User

- Method : PUT
- Endpoint : `/{id}`
- Header :
  - Content-Type: application/json
  - Accept: application/json
- Body :
  ```json
  {
  	"name": "string",
  	"email": "string"
  }
  ```
- Response Status Code : `200`
- Response :
  ```json
  {
  	"status": "string",
  	"msg": "string"
  }
  ```

#### D. Update User

- Method : DELETE
- Endpoint : `/{id}`
- Header :
  - Accept: application/json
- Response Status Code : `200`
- Response :
  ```json
  {
  	"status": "string",
  	"msg": "string"
  }
  ```

## Docker

### Container pada Docker

Container berfungsi sebagai tempat menyimpan seluruh dependensi yang diperlukan oleh sebuah software tertentu agar dapat berjalan. Container ini menghindarkan user dari masalah kompatibilitas yang mungkin akan terjadi pada beberapa sistem yang berbeda.

### Basic Penggunaan dari Docker

- docker pull

  Perintah untuk download image dari docker hub

  ```bash
  docker pull chuanwen/cowsay
  ```

- docker images

  Perintah untuk menampilkan list images yang sudah terdownload

  ```bash
  docker images
  ```

- docker run

  Perintah untuk menjalankan container

  ```bash
  docker run
  ```

- docker ps

  Perintah untuk menampilkan list container yang sedang berjalan

  ```bash
  docker ps
  ```

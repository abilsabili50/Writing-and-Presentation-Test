# **Writing and Presentation Test Week 7**

## List Materi :

1. [Sequelize](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#sequelize)
2. [MongoDB](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#mongodb) - going to be added
3. [Mongoose](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#mongoose) - going to be added
4. [Docker](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-7#docker) - going to be added

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

## Docker

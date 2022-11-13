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

## Mongoose

## Docker

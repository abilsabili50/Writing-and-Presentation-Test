# **Writing and Presentation Test Week 4**

## List Materi :

1. [Javascript Fetch](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#javascript-fetch)
2. [Git & Github Lanjutan](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#git--github-lanjutan) - going to be added
3. [Responsive Web Design](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#responsive-web-design) - going to be added
4. [Bootstrap](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#bootstrap) - going to be added

## Javascript Fetch

Fetch merupakan built-in function yang sering digunakan untuk berinteraksi pada suatu API endpoint baik itu mengambil, menambah, mengedit, bahkan menghapus data. Fetching API adalah fitur terbaru dari javascript versi ES6. Berikut format syntax dari fetch :

```js
fetch(URL);
```

> URL merupakan endpoint yang akan dilakukan interaksi.

Namun, perlu dipahami bahwa fetch sangat berhubungan erat dengan `promises`. Oleh karena itu, kita perlu mengatasinya baik dengan chaining `then...catch` maupun menggunakan `async-await`.

Berikut contoh penerapan fetch :

```js
// chaining
fetch("https://digimon-api.vercel.app/api/digimon")
	.then((response) => response.json())
	.then((response) => console.log(response))
	.catch((error) => console.log(error));

// menggunakan async-await
const ambilData = async () => {
	try {
		const response = await fetch("https://digimon-api.vercel.app/api/digimon");
		const data = await response.json();
		console.log(data);
	} catch (error) {
		console.log(error.message);
	}
};
```

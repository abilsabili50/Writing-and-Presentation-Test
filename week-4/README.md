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

## Git & Github Lanjutan

Git dan github merupakan tools yang wajib dikuasai khususnya oleh para developer. Hal ini dikarenakan git dan github dapat mengatur versioning dari sebuah produk digital yang kita buat. Sedangkan, untuk perbedaan dari keduanya yaitu github merupakan git yang berbasis cloud. Repository yang ada pada github biasa disebut sebagai remote repo. Untuk dapat menghubungkan repo local ke repo github dapat menggunakan command berikut :

1. ### Git Remote

   Git remote digunakan untuk menghubungkan antara repo local ke repo cloud (github, gitlab, dll).

   ```bash
   git remote add <var> <url>
   ```

   > var akan menjadi nama variable remote
   >
   > url merupakan lokasi repo yang akan dijadikan remote

   Berikut contoh penerapannya :

   ```bash
   git remote add origin https://github.com/abilsabili50/Writing-and-Presentation-Test.git
   git remote add development https://github.com/abilsabili50/Writing-and-Presentation-Test.git
   ```

2. ### Git Push

   Git push digunakan untuk memperbarui perubahan yang terjadi pada local kepada repo cloud.

   ```bash
   git push <var> <branch>
   ```

   > var akan menjadi nama variable dari remote yang akan dituju
   >
   > branch akan menjadi nama branch yang akan dipush ke remote

   Berikut contoh penerapannya :

   ```bash
   git push origin main
   ```

3. ### Git Merge

Pada minggu sebelumnya telah diketahui bahwa git merge berfungsi untuk menggabungkan sebuah cabang ke cabang yang lain. Terdapat beberapa tipe merging, antara lain :

    - #### Fast Forward Merge

    	Fast forward merge merupakan merging 1 jalur, sehingga teknik merge yang seperti ini jarang ditemui sebuah konflik. Namun, teknik ini jarang terjadi pada saat berkolaborasi. Berikut contoh penggambarannya.

    	![image](https://user-images.githubusercontent.com/73186952/195801988-67ac65c3-7c0a-4792-9fb5-aea2f6583905.png)

    - #### Three Way Merge

    		Three way merge merupakan teknik merging dengan lebih dari 1 jalur, sehingga teknik merge ini seringkali terjadi sebuah konflik. Konflik biasa terjadi apabila terdapat terdapat 2 perubahan yang terjadi pada file dan baris yang sama. Saat konflik terjadi biasanya kita disuruh memilih perubahan mana yang akan dipakai, sehingga perubahan lainnya akan dihapus. Berikut contoh penggambarannya.

    		![image](https://user-images.githubusercontent.com/73186952/195802762-9d52b6e3-d135-4e47-ab8f-1e2a255f2eec.png)

4. ### Git Clone

   Git clone digunakan untuk menyalin repo cloud pada repo local.

   ```bash
   git clone <url>
   ```

   > url akan menjadi lokasi dari repo yang akan disalin pada sistem local.

   Berikut contoh penerapannya :

   ```bash
   git clone https://github.com/abilsabili50/Writing-and-Presentation-Test.git
   ```

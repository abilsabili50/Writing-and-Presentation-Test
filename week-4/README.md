# **Writing and Presentation Test Week 4**

## List Materi :

1. [Javascript Fetch](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#javascript-fetch)
2. [Git & Github Lanjutan](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#git--github-lanjutan)
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

5. ### Github Organization

   Git organization merupakan sebuah wadah yang disediakan oleh github untuk dapat melakukan kolaborasi. Untuk membuat github organization dapat dilakukan dengan cara-cara berikut :

   1. Klik tombol (+) yang ada di kanan atas pada halaman github. Nanti akan muncul sebuah dropdown
   2. Dari dropdown tersebut klik tombol new organization.
   3. Setelah itu, pilih opsi sesuai yang ingin dibuat.
   4. Input nama dan email organisasi.

## Responsive Web Design

Responsive web design merupakan suatu konsep yang mengharuskan kita dalam membuat design yang dapat kompatibel pada seluruh jenis device (mobile - wide screen monitor).

1. ### Developer Tools

   Sebagai developer website kita perlu mengetahui cara penggunaan tools-tools dari setiap browser. Contohnya pada browser chrome cara pengaksesan dev toolsnya dapat menggunakan command berikut :

   `Mac`

   ```bash
   cmd + opt + j
   ```

   `Windows`

   ```bash
   ctrl + shift + j
   ```

2. ### Viewport

   Untuk menerapkan konsep responsive design, perlu menambahkan tag meta viewport agar mendukung perubahan design. Tag meta tersebut dapat ditambahkan di dalam tag head pada HTML.

   ```html
   <!DOCTYPE html>
   <html lang="en">
   	<head>
   		<meta charset="UTF-8" />
   		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
   		<title>Document</title>
   	</head>
   	<body></body>
   </html>
   ```

3. ### CSS Relative Units

   Dalam penerapan konsep responsive design kita dapat menggunakan CSS relative units. Ada beberapa css relative units, antara lain :

   - #### %

     `%` relatif terhadap elemen parent-nya. Berikut contoh penggunaanya:

     ```css
     .container {
     	width: 60%;
     }
     ```

     > maka ukuran container akan menjadi 60% relatif terhadap body

   - #### Rem

     `rem` relatif ukuran dari root element-nya. Berikut contoh penggunaanya:

     ```css
     html {
     	font-size: 20px;
     }
     p {
     	font-size: 2rem;
     }
     ```

     > maka ukuran dari `p` menjadi 40px

   - #### Em

     `em` relatif terhadap elemen parent-nya, mirip seperti `%`. Berikut contoh penggunaannya:

     ```css
     html {
     	font-size: 20px;
     }
     .container {
     	font-size: 10px;
     }
     .container p {
     	font-size: 2em;
     }
     ```

     > maka ukuran dari `p` menjadi 20px

   - #### Vw

     `vw` seperti `%`, tetapi relatif terhadap lebar layar device. Berikut contoh penggunaanya:

     ```css
     .container {
     	width: 80vw;
     }
     ```

     > maka ukuran lebar dari container akan 80% terhadap lebar layar

   - #### Vh

     `vh` mirip seperti `vw`, tetapi bukan lebay layar melainkan tinggi layar device. Berikut contoh penggunaannya:

     ```css
     .container {
     	height: 20vh;
     }
     ```

     > maka ukuran tinggi dari container akan 20% terhadap tinggi layar

4. ### Media Query

   Media query merupakan sebuah metode untuk menerapkan design dengan karakteristik berbeda-beda yang berbasis pada sesuatu. Sesuatu yang disebutkan disini dapat berupa ukuran layar maupun aksi seperti print dan lain-lain. Media query dapat digunakan untuk menjadikan design dapat mengusung konsep responsive design. Berikut contoh penggunaannya pada responsive design:

   ```css
   @media screen and (min-width: 800px) {
   	.container {
   		backround-color: blue;
   	}
   }

   @media screen and (max-width: 800px) {
   	.container {
   		background-color: red;
   	}
   }
   ```

   > Background color `container` akan berwarna biru jika layar berukuran > 800px
   >
   > Background color `container` akan berwarna merah jika layar berukuran < 800px

5. ### Flexbox
   Flexbox

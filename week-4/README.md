# **Writing and Presentation Test Week 4**

## List Materi :

1. [Javascript Fetch](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-4#javascript-fetch)
2. [Git & Github Lanjutan](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-4#git--github-lanjutan)
3. [Responsive Web Design](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-4#responsive-web-design)
4. [Bootstrap](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-4#bootstrap)

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

   Flexbox memungkinkan sebuah container mengubah lebar/tinggi seluruh elemen didalamnya sesuai dengan ruang yang tersedia.

   - #### Flex Container
     Terdapat beberapa properti flex pada container, antara lain:
     - flex-direction
       ```css
       display: flex;
       flex-ditection: row | column;
       ```
     - flex-wrap
       ```css
       display: flex;
       flex-wrap: nowrap | wrap;
       ```
     - justify-content
       ```css
       display: flex;
       justify-content: center | flex-start | flex-end | space-around |
       	space-between | space-evenly;
       ```
     - align-items
       ```css
       display: flex;
       align-items: center | flex-start | flex-end | stretch | baseline;
       ```
     - align-content
       ```css
       display: flex;
       align-content: space-between | space-around | stretch | center |
       	flex-start | flex-end;
       ```
   - #### Flex Items
     Terdapat beberapa properti flex pada item dalam sebuah flex-container, antara lain:
     - order
     ```css
     order: 3;
     ```
     - flex-grow
     ```css
     flex-grow: 8;
     ```
     - flex-shrink
     ```css
     flex-shrink: 0;
     ```
     - flex-basis
     ```css
     flex-basis: 200px;
     ```
     - align-self
     ```css
     align-self: center | flex-start | flex-end;
     ```

6. ### Grid

   Grid merupakan sebuah sistem tata letak 2 dimensi yang dimiliki oleh CSS. Grid memungkinkan kita menempatkan konten sesuai dengan yang kita inginkan.

   ![image](https://user-images.githubusercontent.com/73186952/196040745-da057218-f535-491e-9d09-dca6d090a36e.png)
   _sumber: [css-tricks](https://css-tricks.com/snippets/css/complete-guide-grid/)_

   - #### Grid Container Property

     Sebelum menggunakan grid, perlu diinisialisasi terlebih dahulu `display` dari konten dengan value `grid` atau `inline-grid`. Ada beberapa property pada grid container, antara lain:

     1. grid-template-columns

        ```css
        .container {
        	display: grid;
        	grid-template-columns: 100px 100px 100px 100px;
        }
        ```

        > kode diatas menghasilkan 4 kolom dengan ukuran `100px`

     2. grid-template-rows

        ```css
        .container {
         display: grid;
         height: 100px
         grid-template-rows: 1fr 1fr 1fr 1fr;
        }
        ```

        > kode diatas menghasilkan 4 baris dengan ukuran yang sama yaitu `25px`

     3. justify-content

        ```css
        .container {
        	display: grid;
        	justify-content: space-evenly | space-between | space-around | center
        		| start | end;
        }
        ```

        > `justify-content` berfungsi untuk meluruskan seluruh item didalam grid-container

     4. align-content

        ```css
        .container {
        	display: grid;
        	align-content: space-evenly | space-between | space-around | center |
        		start | end;
        }
        ```

        > `align-content` berfungsi untuk meluruskan seluruh item didalam grid-container secara vertikal

     5. gap

        ```css
        .container {
        	display: grid;
        	gap: 50px | 50px 100px;
        	column-gap: 50px;
        	row-gap: 50px;
        }
        ```

        > `gap` berfungsi untuk memberi ruang antar item yang ada didalam grid-container

     6. grid-template-area

        ```css
        .container {
        	display: grid;
        	grid-template-areas:
        		"header header header header header header"
        		"menu main main main right right"
        		"menu footer footer footer footer footer";
        }
        ```

   - #### Grid Item Property

     1. grid-column

        ![image](https://user-images.githubusercontent.com/73186952/196075448-7fe92b97-c3f9-4696-a78b-9f12a5295624.png)

        _sumber: [w3school](https://www.w3schools.com/css/css_grid_item.asp)_

        ```css
        .item-1 {
        	grid-column: 1 / 5;
        }
        .item-2 {
        	grid-column: 1 / span 5;
        }
        ```

        > Panjang `item-1` akan mulai dari kolom 1 sampai sebelum kolom ke-5
        >
        > Panjang `item-2` akan mulai dari kolom 1 dan melebar sebanyak 5 kolom

     2. grid-row

        ![image](https://user-images.githubusercontent.com/73186952/196075719-478011f4-7ed3-424d-bf7d-7394fdd60409.png)

        _sumber: [w3school](https://www.w3schools.com/css/css_grid_item.asp)_

        ```css
        .item-1 {
        	grid-row: 1 / 5;
        }
        .item-2 {
        	grid-row: 1 / span 5;
        }
        ```

        > Panjang `item-1` akan mulai dari baris 1 sampai sebelum baris ke-5
        >
        > Panjang `item-2` akan mulai dari baris 1 dan melebar sebanyak 5 baris

     3. grid-area

        ```css
        .grid-container {
        	grid-template-areas:
        		"header header header header header header"
        		"menu main main main right right"
        		"menu footer footer footer footer footer";
        }
        .item1 {
        	grid-area: header;
        }
        .item2 {
        	grid-area: menu;
        }
        .item3 {
        	grid-area: main;
        }
        .item4 {
        	grid-area: right;
        }
        .item5 {
        	grid-area: footer;
        }
        ```

        > `grid-area` berfungsi untuk menempatkan grid-item pada grid-template-area yang telah disediakan oleh grid-container

## Bootstrap

- ### Penggunaan Bootstrap

  Bootstrap merupakan salah satu dari banyaknya framework CSS. Banyak yang menggunakan bootstrap dikarenakan framework ini sangat user-friendly bagi pemula khususnya saya. Framework ini direkomendasikan jika ingin membuat web design yang sederhana dan bahkan yang lumayan kompleks pun bisa. Penggunaannya cukup mudah, dapat menggunakan cdn link maupun install package-nya juga bisa.

  #### CDN Links

  | Deskripsi | URL                                                                          |
  | --------- | ---------------------------------------------------------------------------- |
  | CSS       | https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/css/bootstrap.min.css      |
  | JS        | https://cdn.jsdelivr.net/npm/bootstrap@5.2.2/dist/js/bootstrap.bundle.min.js |

  Setelah include package bootstrap, untuk penggunaannya cukup mudah yaitu hanya berbasis class utility.

  ```html
  <p class="text-danger">Hello World</p>
  ```

  > `text-danger` akan merubah warna text menjadi merah

- ### Layouting Pada Bootstrap

  Untuk mengatur layouting pada bootstrap dapat menggunakan hierarki `row-col`. Berikut contoh penerapannya.

  ```html
  <div class="row">
  	<div class="col">
  		<p>Hello World</p>
  	</div>
  </div>
  ```

  Hierarki kolom pada bootstrap terdapat 12 kolom, sehingga kita bisa menambahkan lebar kolom dengan jumlah maksimal 12. Berikut contoh penerapannya.

  ```html
  <div class="row">
  	<div class="col-4">
  		<p>Kolom-1</p>
  	</div>
  	<div class="col-4">
  		<p>Kolom-2</p>
  	</div>
  	<div class="col-4">
  		<p>Kolom-3</p>
  	</div>
  </div>
  ```

  > kode diatas akan menghasilkan 3 kolom dengan ukuran yang sama

  #### Breakpoints

  | Breakpoints       | Class | Dimension |
  | ----------------- | ----- | --------- |
  | Small             | sm    | >= 576px  |
  | Medium            | md    | >= 768px  |
  | Large             | lg    | >= 992px  |
  | Extra Large       | xl    | >= 1200px |
  | Extra Extra Large | xxl   | >= 1400px |

- ### Content Bootstrap

  Beberapa content bootstrap adalah typography, images, tables, dan lain-lain.

  #### Typography

  ```html
  <p class="h1">Hello World</p>
  <p class="h3">Hello World</p>
  <p class="h6">Hello World</p>
  ```

  #### Images

  ```html
  <img src="..." class="img-fluid" alt="..." />
  <img src="..." class="img-thumbnail" alt="..." />
  ```

- ### Component Bootstrap

  Ada banyak sekali component pada bootstrap seperti alert, card, badge, modal, navbar, dan lain-lain. Berikut beberapa penggunaan component-nya.

  #### Alert

  ```html
  <div class="alert alert-primary" role="alert">
  	A simple primary alert—check it out!
  </div>
  ```

  _Output_:
  ![image](https://user-images.githubusercontent.com/73186952/196158469-64763244-eb4c-4958-a53b-651cd16fc985.png)

  #### Card

  ```html
  <div class="card" style="width: 18rem;">
  	<img src="..." class="card-img-top" alt="..." />
  	<div class="card-body">
  		<h5 class="card-title">Card title</h5>
  		<p class="card-text">
  			Some quick example text to build on the card title and make up the bulk
  			of the card's content.
  		</p>
  		<a href="#" class="btn btn-primary">Go somewhere</a>
  	</div>
  </div>
  ```

      _Output_:
      ![image](https://user-images.githubusercontent.com/73186952/196159078-f1e02c2d-b798-417f-806a-db7d3f7aed5e.png)

- ### Contoh Hasil Website Menggunakan Bootstrap

  Untuk melihat kode yang telah saya buat dapat dilihat pada repo [ini](https://github.com/abilsabili50/SkilMovie).Sedangkan, Untuk contoh hasil website yang telah saya buat dapat dilihat [disini](https://movies-apps.vercel.app/).

- ### Untuk lebih lanjut dapat melihat dokumentasinya [disini](https://getbootstrap.com/docs/5.2/getting-started/introduction/)

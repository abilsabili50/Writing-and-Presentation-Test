# **Writing and Presentation Test Week 3**

## List Materi :

1. [Javascript Array & Multidimensional Array](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#array--multidimensional-array)
2. [Javascript Object](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#object)
3. [Javascript Rekursif](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#rekursif)
4. [Javascript Web Storage](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#web-storage)
5. [Javascript Asynchronous](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#asynchronous)

## Array & Multidimensional Array

Array adalah sebuah tipe data yang dapat menyimpan tipe data apapun didalamnya. Pembuatan array menggunakan sebuah keyword `[]`.

```js
const arr = ["String", 2, true, { nama: "Abil" }];
console.log(arr[1]); // 2
```

- ### Array Properties

  1. constructor
  2. length
  3. index
  4. prototype
  5. dll

- ### Array Method

  - #### Manipulation Method

    1. .unshift() / .push(), untuk menambahkan data di awal / terakhir pada sebuah array.
    2. .shift() / .pop(), untuk mengambil data di awal / terakhir dari sebuah array.
    3. .sort(), untuk mengurutkan data pada array.
    4. dll

    contoh kode :

    ```js
    const arr = [2, 3, 7, 8, 4, 2];
    arr.unshift(1); // arr = [1, 2, 3, 7, 8, 4, 2]
    arr.push(0); // arr = [1, 2, 3, 7, 8, 4, 2, 0]

    console.log(arr.shift()); // 1, arr = [2, 3, 7, 8, 4, 2, 0]
    console.log(arr.pop()); // 0, arr = [2, 3, 7, 8, 4, 2]

    arr.sort(); // arr = [2, 2, 3, 4, 7, 8]
    ```

  - #### Looping Method

    1. .forEach(), untuk melakukan looping pada setiap array.
    2. .map(), untuk melakukan looping dan membuat array baru.
    3. dll

    Contoh kode :

    ```js
    const arr = [1, 2, 3, 4, 5];

    arr.forEach((element) => console.log(element)); // 1, 2, 3, 4, 5

    arr = arr.map((element) => element * 2); // arr = [2, 4, 6, 8, 10]
    ```

    Selain menggunakan lopping method dari sebuah array, kita dapat juga menggunakan looping `for(...of...)`. Berikut contoh penggunaannya :

    ```js
    const arr = ["Abil", "Syagi", "Fahrul"];

    for (let element as arr){
      console.log(element);
    }
    // Abil
    // Syaugi
    // Fahrul
    ```

- ### Array Multidimensional

  Array multidimensional adalah sebuah konsep dari nested array (array yang berisi sebuah array lagi). Biasanya untuk mengakses data didalamnya dapat menggunakan kurung siku (`[]`) yang sesuai dengan banyak nested didalam array tersebut.

  Contoh penggunaanya :

  ```js
  const arr = [
  	[1, 2],
  	[3, 4],
  ];

  console.log(arr[0][0]); // 1
  console.log(arr[0][1]); // 2
  console.log(arr[1][0]); // 3
  console.log(arr[1][1]); // 4
  ```

## Object

Object adalah sebuah tipe data yang dapat menyimpan properti dan method. Properti yang disimpan dapat berupa tipe data lain atau bahkan tipe data object lagi. Sedangkan, method akan berfungsi sebagai aksi dari object sehingga dapat menyimpan function. Dalam pembuatan object digunakan keyword kurung kurawal `{}`.

Contoh pembuatan object :

```js
const kucing = {
	tipe: "hewan",
	kaki: 4,
	lari: () => {
		console.log("kucing sedang berlari");
	},
};

console.log(kucing.tipe); // hewan
```

Kita dapat menggunakan looping untuk mengakses sebuah object, yaitu menggunakan looping `for(...in...)`. Berikut contoh kodenya :

```js
const avanza = {
  tipe: "mobil",
  asal: "china",
  tahun: 2012,
}

for(let key as avanza){
  console.log(avanza[key]);
}
// mobil
// china
// 2012
```

- ### Array of Object

  Array of object merupakan konsep kombinasi penggunaan tipe data array dan object, dimana sebuah array nanti dapat berisi banyak object.

  Contoh pembuatan array of object :

  ```js
  const mahasiswa = [
  	{
  		nama: "Abil",
  		jk: "Pria",
  		umur: 20,
  	},
  	{
  		nama: "Syaugi",
  		jk: "Pria",
  		umur: 20,
  	},
  	{
  		nama: "Dinda",
  		jk: "Wanita",
  		umur: 21,
  	},
  ];

  console.log(mahasiswa[0].nama); // Abil
  console.log(mahasiswa[2].jk); // Wanita
  ```

## Rekursif

Rekursif merupakan sebuah fungsi yang memanggil dirinya sendiri hingga mencapai suatu kondisi tertentu. Kondisi tertentu tersebut yang akan menjadi kondisi yang menyatakan bahwa fungsi tersebut akan berhenti.

Contoh gambaran rekursif :

```js
function myfunc() {
  ...
	myFunc();
  ...
}
```

Contoh penggunaan fungsi rekursif :

```js
function factorial(start) {
	return start <= 1 ? 1 : start * factorial(start - 1);
}
```

## Web Storage

Web storage adalah sebuah metode yang sering digunakan untuk menyimpan data sementara pada sisi klien (client-side), seperti menyimpan data tema website. Terdapat beberapa macam web storage yang sering digunakan, antara lain :

1. ### Cache
   Cache adalah teknologi yang ada didalam web browser untuk menyimpan data ketika website dimuat pertama kali berupa asset (gambar, file, dll), sehingga saat website tersebut dibuka kembali akan menjadi lebih cepat.
2. ### Cookies
   Cookies adalah bagian kecil dari data yang dikirim oleh sebuah website pada saat website tersebut dibuka oleh pengguna. Cookies biasa digunakan untuk menyimpan informasi login, configurasi bahasa, dan lain-lain.
3. ### Session Storage
   Session storage adalah penyimpanan website yang memungkinkan kita untuk menyimpan data pada sisi klien (client-side) selama web browser belum ditutup atau keluar. Berikut contoh penggunaan session storage :
   ```js
   sessionStorage.setItem("variabel", "value"); // untuk menyimpan data pada session storage
   sessionStorage.getItem("variabel"); // untuk mengambil data pada session storage
   sessionStorage.removeItem("variabel"); // untuk menghapus data pada session storage
   sessionStorage.clear(); // untuk menghapus seluruh data pada session storage
   ```
   > `variabel` sebagai key pada session storage
   > `value` sebagai nilai dari suatu key pada session storage
4. ### Local Storage
   Local storage adalah jenis penyimpanan yang hampir sama seperti session storage, tetapi tanpa batas waktu dengan kata lain tidak akan hilang walaupun web browser ditutup atau keluar. Berikut contoh penggunaan local storage :
   ```js
   localStorage.setItem("variabel", "value"); // untuk menyimpan data pada local storage
   localStorage.getItem("variabel"); // untuk mengambil data pada local storage
   localStorage.removeItem("variabel"); // untuk menghapus data pada local storage
   localStorage.clear(); // untuk menghapus seluruh data pada local storage
   ```
   > `variabel` sebagai key pada local storage
   > `value` sebagai nilai dari suatu key pada local storage

## Asynchronous

Pada dasarnya javascript adalah bahasa pemrogramman yang bersifat single-thread dan non-blocking. Single thread disini berarti hanya bisa mengeksekusi satu tugas pada satu waktu atau biasa disebut synchronous. Namun, dengan adanya non-blocking javascript memungkinkan untuk melakukan sebuah program yang asynchoronous yaitu mengeksekusi tugas lain tanpa menunggu tugas sebelumnya selesai terlebih dahulu, sehingga hal ini bisa dikatakan javascript tidak murni memiliki sifat asynchronous. Namun, javascript memanfaatkan sifatnya yang non-blocking untuk mengeksekusi program seolah-olah seperti asynchronous. Asynchronous selalu identik dengan 3 kata kunci yaitu :

1. ### Callback

   Callback function adalah sebuah function yang berada didalam function lain dan proses pengeksekusiannya setelah function diluarnya selesai dijalankan. Berikut contoh dari callback function :

   ```js
   setTimeout(() => {
   	console.log("dijalankan setelah beberapa detik");
   }, 3000);
   ```

   > parameter pertama dari function setTimeout merupakan sebuah callback
   >
   > parameter kedua dari function setTimeout merupakan sebuah lama delay sebelum menjalankan sebuah callbacknya.

2. ### Promises

   Promise adalah adalah sebuah object yang memungkinkan pengembalian nilainya dilakukan pada masa yang akan datang. Promise bisa ditangani dengan menggunakan method chaining dari object promise sendiri berupa `then()` dan `catch()`. Nilai yang dapat dikembalikan oleh object promise antara lain :

   - #### Fulfilled, nilai kembalian yang akan dikembalikan jika proses pengeksekusian promise telah selesai dan berhasil.
   - #### Pending, nilai kembalian yang akan dikembalikan jika proses pengeksekusian promise masih belum selesai.
   - #### Rejected, nilai kembalian yang akan dikembalikan jika proses pengeksekusian promise telah selesai, tetapi gagal dilakukan.

   Contoh implementasi promise :

   ```js
   function promiseFunc(param) {
   	return new Promise((resolve, reject) => {
   		if (!param) reject("param tidak ada");
   		resolve(`param ${param} ada`);
   	});
   }
   ```

   > resolve akan masuk kedalam then.
   >
   > reject akan masuk kedalam catch.

3. ### Async / Await

   Async dan await merupakan salah satu fitur baru dari javascript yang digunakan untuk menangani hasil dari promise selain menggunakan chaining. `async` berfungsi untuk penginisialisasian bahwa didalam blok tersebut akan terdapat asynchronous proses. Sedangkan, `await` berfungsi sebagai penanda proses mana yang berjalan secara asynchronous, sehingga proses dibawahnya tidak akan dieksekusi sebelum proses asynchronousnya selesai terlebih dahulu.

   Contoh implementasi `async-await` :

   ```js
   async function greeting() {
   	let greet = await "Halo";
   	return greet;
   }

   const greeting = async () => {
   	let greet = await "Halo";
   	return greet;
   };
   ```

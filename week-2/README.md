# **Writing and Presentation Test Week 2**

## List Materi :

1. [Javascript Scope](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-2#scope)
2. [Javascript Function](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-2#function)
3. [Javascript DOM](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-2#document-object-model) - going to be added

## Scope

Scope adalah konsep dalam flow data variable. Untuk penentuan scope biasanya digunakan blocks atau `{ ... }`. Conditional, function, dan looping mengusung konsep scope.

- #### Global Scope

  merupakan salah satu sifat scope yang menjadikan suatu variable dapat diakses dimanapun dalam suatu file.

  **Contoh Kode :**

  ```js
  let myName = "Abil";
  {
  	console.log(myName); // Abil
  }
  ```

- #### Local Scope

  Local scope merupakan sifat dari variable yang hanya bisa diakses didalam scope tersebut saja.

  **Contoh Kode :**

  ```js
  {
  	let myName = "Abil";
  	console.log(myName); // Abil
  }
  console.log(myName); // Error, myName is not defined
  ```

## Function

Merupakan sebuah blok kode program yang digunakan untuk menyelesaikan sebuah tugas, sehingga nantinya dapat digunakan kembali jika menemukan kasus tugas yang sama. Javascript dikenal powerfull karena functional programming-nya. Terdapat berbagai macam cara dalam membuat sebuah function, antara lain :

1. menggunakan keyword function
   Cara ini merupakan cara dasar dalam mendeklarasikan sebuah function. Berikut struktur kode nya :

   ```js
   function namaFunction(parameter1, parameter2) {
   	statement;
   }
   ```

   Contoh penerapan :

   ```js
   // function yang mengembalikan nilai
   function sum(nilai1, nilai2) {
   	return nilai1 + nilai2;
   }

   // function yang tidak mengembalikan nilai
   function sum(nilai1, nilai2) {
   	console.log(nilai1 + nilai2);
   }
   ```

2. menggunakan arrow function
   Cara ini merupakan fitur terbaru dari ES6 yang menjadi cara lain dalam menuliskan function. Berikut struktur kode nya :

   ```js
   const namaFunction = (parameter1, parameter2, ...) => {
   	statement;
   };
   ```

   Contoh penerapan :

   ```js
   const sum = (nilai1, nilai2) => { return nilai1 + nilai2 };
   const sum = (nilai1, nilai2) => { nilai1 + nilai2 }; // ini sama dengan kode diatas
   const sum = (nilai1, nilai2) => { console.log(nilai1 + nilai2) };
   ```
   > Pada penulisan oneline arrow function keyword return dapat ditiadakan karena pada contoh function sum yang kedua javascript akan mengembalikan secara otomatis `nilai1` `+` `nilai2`.

Kemudian untuk memanggil function yang telah dibuat tersebut kita dapat menggunakan kode seperti berikut :

```js
const returningSum = (nilai1, nilai2) => { nilai1 + nilai2 };
const sum = (nilai1, nilai2) => { console.log(nilai1 + nilai2) };

returningSum(1, 2); // tidak akan menampilkan apa-apa
sum(1, 2); // menampilkan nilai 3

console.log(returningSum(1, 2)); // menampilkan nilai 3
console.log(sum(1, 2)); // menampilkan nilai 3 + value undefined karena == console.log(console.log(1 + 2))
```

### Parameter & Argumen

#### Parameter

Parameter adalah sebuah inputan data yang dibuat saat pendefinisian function. Dengan parameter, function dapat menerima inputan saat pemanggilannya.

Contoh parameter : 

```js
function namaFunction (parameter1, parameter2, ..., parameter-N){
  statement;
}
```

> parameter1, parameter2, hingga parameter-N merupakan parameter.

#### Default parameter

Default parameter adalah sebuah parameter yang sudah memiliki nilai default saat didefinisikan. Nilai default akan digunakan apabila saat pemanggilannya tidak menyertakan argumen yang dibutuhkan. Contoh kode :

```js
function namaFunction (param1 = "Nilai Default", param2, ...){
  statement;
}
```


#### Argumen

Argumen adalah sebuah data yang digunakan saat memanggil function. Contoh penggunaan argumen adalah seperti berikut :

```js
namaFunction(argumen1, argumen2, ..., argumen-N);
```

> banyak argumen yang digunakan direkomendasikan sama dengan parameter yang telah didefinisikan sebelumnya.

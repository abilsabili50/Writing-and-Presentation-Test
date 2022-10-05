# **Writing and Presentation Test Week 3**

## List Materi :

1. [Javascript Array & Multidimensional Array](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#array--multidimensional-array)
2. [Javascript Object](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#object)
3. [Javascript Rekursif](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#rekursif) - going to be added
4. [Javascript Web Storage](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#web-storage) - going to be added
5. [Javascript Asynchronous](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-3#asynchronous) - going to be added

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

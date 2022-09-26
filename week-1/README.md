# **Writing and Presentation Test Week 1**

## List Materi :

1. [Unix Command Line](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#unix-command-line)
2. [Git & Github](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#git--github)
3. [HTML](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#html)
4. [CSS](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#css)
5. [Algorithm](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#algorithm)
6. [Javascript](https://github.com/abilsabili50/Writing-and-Presentation-Test/tree/main/week-1#javascript) - going to be added

## Unix Command Line

Command line adalah sebuah mekanisme untuk berinteraksi dengan sistem operasi atau perangkat lunak komputer. Sedangkan, CLI (command line interface) adalah antarmuka untuk menuliskan perintah-perintah tersebut. Contoh dari CLI seperti :

- bash
- cmd.exe
- dst

### Unix Command - Navigasi

#### **pwd**

`pwd` command digunakan untuk menampilkan directory sedang digunakan. Contoh command :

```bash
pwd
```

#### **ls**

`ls` command digunakan untuk menampilkan isi dari directory yang sedang digunakan. Contoh command :

```bash
ls
```

#### **cd**

`cd` command digunakan untuk berpindah directory. Contoh command

```bash
cd <dirpath>
```

> `dirpath` berisi lokasi directory yang akan dituju.
>
> `dirpath` dapat relatif maupun absolut path.

### Unix Command - Manipulasi

#### **touch**

`touch` command digunakan untuk membuat sebuah file pada directory yang sedang digunakan. Contoh command :

```bash
touch <filename>
```

> `filename` berisi nama file yang akan dibuat beserta ekstensinya.

#### **mkdir**

`mkdir` command digunakan untuk membuat sebuah directory didalam directory yang sedang digunakan. Contoh command :

```bash
mkdir <dirname>
```

> `dirname` berisi nama directory yang akan dibuat.

#### **cp**

`cp` command digunakan untuk menyalin file/directory. Contoh command :

```bash
cp <param1> <param2>
```

> `param1` berisi nama file atau nama directory.
>
> `param2` berisi nama directory yang akan menjadi tempat salinan.
>
> > Khusus untuk menyalin directory tambahkan `-r` sebelum `param1`.

#### **mv**

`mv` command digunakan untuk memindahkan file. Command ini juga bisa digunakan untuk mengubah nama file. Contoh command :

```bash
mv <param1> <param2>
```

> `param1` berisi nama file.
>
> `param2` berisi nama directory yang akan menjadi tempat salinan.
>
> `param2` dapat berisi nama file yang akan menjadi nama baru dari file pada `param1`.

#### **rm**

`rm` command digunakan untuk menghapus sebuah file/directory. Contoh command :

```bash
rm <param1>
```

> `param1` berisi nama file atau nama directory.
>
> > Khusus untuk menghapus directory tambahkan `-r` sebelum `param1`.

### Unix Command - Menampilkan Isi File

#### **head**

`head` command digunakan untuk menampilkan 10 baris pertama dari isi file. Contoh command :

```bash
head <option> <filename>
```

> `option` dapat diisi dengan banyak baris yang ingin ditampilkan **(opsional)**.
>
> `filename` dapat diisi dengan nama file yang ingin dilihat isinya.

#### **tail**

`tail` command digunakan untuk menampilkan 10 baris terakhir dari isi file. Contoh command :

```bash
tail <option> <filename>
```

> `option` dapat diisi dengan banyak baris yang ingin ditampilkan **(opsional)**.
>
> `filename` dapat diisi dengan nama file yang ingin dilihat isinya.

#### **cat**

`cat` command digunakan untuk menampilkan seluruh isi dari sebuah file. Contoh command :

```bash
cat <filename>
```

> `filename` berisi nama file yang ingin ditampilkan isinya.

## Git & Github

Git adalah tools local yang sering digunakan oleh programmer sebagai versioning system untuk project yang sedang dikerjakan. Git berguna untuk melacak perubahan yang terjadi pada sebuah project dan siapa yang merubahnya sehingga mempermudah programmer dalam mengerjakan sebuah project secara tim. Terdapat banyak versi git yang berbasis cloud seperti :

- Github
- Gitlab
- Bitbucket
- Dst...

### Instalasi Git

Klik [disini](https://git-scm.com/downloads) untuk melakukan download git lalu lakukan instalasi seperti instalasi aplikasi pada umumnya.

#### Setup awal

Isi username dan email config sesuai dengan yang digunakan pada github agar langsung diarahkan pada proses login github.

```bash
git config --global user.name "<username>"
git config --global user.email <email>
```

> `username` berisi username.
>
> `email` berisi email yang digunakan pada github.

Untuk melakukan pengecekan keberhasilan instalasi dapat menggunakan command berikut :

```bash
git --version
```

Output :
![image](https://user-images.githubusercontent.com/73186952/192096746-8dcd7083-1eea-4d44-8427-1c80d5992891.png)

#### Git command

- **Git init**

Git init digunakan untuk menginisialisasi folder untuk dijadikan sebagai git repository. Kita bisa menggunakannya dengan command dibawah :

```bash
git init
git init <dirname>
```

> command pertama untuk menginsialisasi folder saat ini.
>
> command kedua untuk membuat folder git baru dengan `dirname` berisi nama folder yang akan digunakan.

- **Git status**

Git status digunakan untuk melihat perubahan dari folder git kita. Contoh command :

```bash
git status
```

- **Git Add**

Git add digunakan untuk memasukkan untracked file (_file baru_) kedalam staging area. Kita bisa melakukannya dengan command dibawah :

```bash
git add .
git add <filename>
```

> command pertma digunakan untuk memasukkan seluruh untracked file ke dalam staging area.
>
> command kedua digunakan untuk spesifik file dengan `filename` berisi nama file yang ingin dimasukkan.

- **Git commit**

Git commit digunakan untuk menyimpan perubahan pada version controll system. Kita dapat melakukannya dengan command dibawah :

```bash
git commit -m "<message>"
```

> `-m` merupakan option untuk menambahkan sebuah message yang diisi pada parameter `message`.

- **Git log**

Git log digunakan untuk melihat riwayat perubahan yang telah disimpan sebelumnya. Kita bisa melakukannya dengan command dibawah :

```bash
git log
git log --oneline
```

> command kedua untuk mempersingkat hasil output yang ditampilkan sehingga bisa mudah dipahami.

- **Git checkout**

Git checkout digunakan untuk membatalkan perubahan sebelum perubahan itu dimasukkan ke staging dan di-commit. Kita dapat melakukannya dengan command dibawah :

```bash
git checkout <filename>
```

> `filename` berisi nama file yang ingin dibatalkan perubahannya.
>
> git checkout juga bisa digunakan untuk pindah ke commit sebelumnya.

- **Git reset**

Git reset digunakan untuk membatalkan perubahan yang telah dicommit. Git reset akan menghapus commit terakhir. Kita dapat melakukannya dengan command dibawah :

```bash
git reset <filename>
```

> `filename` berisi nama file yang ingin dibatalkan perubahannya.
>
> Git reset juga bisa digunakan untuk membatalkan suatu

- **Git revert**

Git revert sama seperti git reset tetapi tanpa menghapus commit terakhir. Kita dapat melakukannya dengan command dibawah :

```bash
git revert -n <hash>
```

> `hash` berisi kode hash commit.

- **Git branch**

Git branch digunakan untuk membuat percabangan agar perubahan yang disimpan pada suatu cabang tidak akan menganggu line utama. Kita dapat melakukannya dengan command dibawah :

```bash
git branch <branch_name>
```

> `branch_name` berisi nama branch yang akan dibuat.
>
> fitur ini biasa digunakan untuk berkolaborasi.

- **Git merge**

Git merge digunakan untuk menggabungkan hasil percabangan ke suatu cabang lain. Kita dapat melakukannya dengan command dibawah :

```bash
git merge <branch_name>
```

> `branch_name` berisi nama branch yang ingin digabungkan ke branch saat ini.

## HTML

Hypertext Markup Language atau biasa disebut HTML merupakan bahasa markup yang digunakan untuk menampilkan konten pada browser. HTML bekerja sebagai kerangka dalam pembuatan website.

### Prerequisite

- Browser (Chrome, firefox, ms. edge)
- Text Editor (VS Code, notepad, notepad++, dst)

### Struktur Dasar HTML

```html
<!DOCTYPE html>
<html lang="en">
	<head>
		<meta charset="UTF-8" />
		<meta http-equiv="X-UA-Compatible" content="IE=edge" />
		<meta name="viewport" content="width=device-width, initial-scale=1.0" />
		<title>Document</title>
	</head>
	<body>
		<!-- isi content -->
	</body>
</html>
```

Kode diatas merupakan struktur dari kode HTML. Konten dari website akan ditempatkan didalam tag body. Terdapat beberapa tag wajib dalam membuat struktur kode HTML, antara lain :

- `<html></html>`
- `<head></head>`
- `<body></body>`

### HTML Elements

#### Element penampil teks

Untuk menampilkan teks kita dapat menggunakan beberapa element HTML seperti :

- HTML Heading
  HTML heading merupakan element penampil teks dengan tingkatan sebagai heading / judul. Didalam HTML heading sendiri terdapat beberapa tingkatan mulai dari `<h1>` yang paling tinggi dan `<h6>` yang paling rendah tingkatannya. Contoh kode :

  ```html
  <h1>Halo dunia</h1>
  ```

- HTML Paragraph
  HTML paragraph merupakan element penampil teks yang berperan sebagai paragraf. Contoh kode :

  ```html
  <p>Ini paragraf</p>
  ```

- HTML Anchor
  HTML anchor merupakan element penampil teks yang berperan sebagai hyperlink. Contoh kode :

  ```html
  <a href="https://google.com/">link menuju google</a>
  ```

#### Element penampil media

- Gambar
  ```html
  <img src="https://bit.ly/3j6eb3B" alt="Cat" />
  ```
- Video
  ```html
  <video>
  	<source src="https://bit.ly/3goJEfJ" type="video/mp4" />
  </video>
  ```
- Suara
  ```html
  <audio>
  	<source src="https://bit.ly/2EbrKA4" type="audio/mp3" />
  </audio>
  ```

#### Element penampil tabel

Untuk menampilkan tabel kita dapat menggunakan tag `<table></table>`. Didalamnya kita dapat menampilkan beberapa element.

- Baris
  Untuk menambahkan baris kita bisa menggunakan tag `<tr></tr>`.
- Kolom
  Untuk menambahkan kolom kita bisa menggunakan tag `<td></td>`.

Sehingga, dari element-element tersebut maka akan terbentuk struktur dasar dari element tabel seperti kode berikut :

```html
<table>
	<tr>
		<td>Baris 1 | Kolom 1</td>
		<td>Baris 1 | Kolom 2</td>
	</tr>
	<tr>
		<td>Baris 2 | Kolom 1</td>
		<td>Baris 2 | Kolom 2</td>
	</tr>
</table>
```

#### Element penampil formulir

Element penampil formulir digunakan untuk menampilkan sebuah form agar user dapat mengisinya. Kita bisa membuat formulir pada HTML menggunakan tag `<form></form>`. Didalamnya terdapat banyak element untuk user dapat mengisi formulirnya, antara lain :

- Input
  Tag input memiliki banyak sekali tipe seperti :

  - text, user mengisi teks,
  - number, user mengisi angka,
  - email, user mengisi email,
  - dan masih banyak lagi.

  Kita bisa membuat input dengan kode seperti berikut :

  ```html
  <input type="text" />
  ```

- Select
  Tag select digunakan untuk memberikan pilihan kepada user, sehingga didalam element select terdapat element option sebagai pilihannya. Berikut contoh kodenya :

  ```html
  <select>
  	<option value="pilihan1">pilihan1</option>
  	<option value="pilihan2">pilihan2</option>
  </select>
  ```

  Output :
  <img width="71" alt="image" src="https://user-images.githubusercontent.com/73186952/192152718-a5df7d36-50d0-448e-b6ad-bbd947516696.png">

- Textarea
  Tag textarea digunakan sebagai tempat untuk user mengirimkan teks yang panjang, biasanya digunakan untuk tempat mengisi pesan. Berikut contoh kodenya :

  ```html
  <textarea></textarea>
  ```

- Tombol
  Kita dapat membuat tombol menggunakan tag button. Berikut contoh kodenya :

  ```html
  <button>Kirim</button>
  ```

  Output :
  ![image](https://user-images.githubusercontent.com/73186952/192156584-5a49dd9e-90af-4ea8-a27e-0cfab1c5da26.png)

## CSS

Cascading Style Sheet atau biasa disebut CSS merupakan style sheet language yang sering digunakan dalam mengatur styling pada halaman website. Oleh karena itu, CSS sering dianalogikan menjadi penampilan dari website.

### Struktur CSS

![image](https://user-images.githubusercontent.com/73186952/192242910-bb830f60-a41f-4fcd-a545-2bf7f9b3bf30.png)<br/>

Terdapat 3 komponen penting pada struktur CSS, yaitu :

1. selector, sebagai penentu element mana yang akan diberi style (dapat berupa tag element HTML, serta value dari attribute id atau class).

```css
/* menggunakan element HTML */
h1 {
	color: red;
}
/* menggunakan class selector */
.header {
	color: red;
}
/* menggunakan id selector */
#main {
	color: red;
}
/* menggunakan chaining selector */
div#main {
	color: red;
}
/* menggunakan nested selector */
body div#main {
	color: red;
}
/* menggunakan multiple selector */
h1,
h2 {
	color: red;
}
```

2. property, sebagai penentu style yang akan dibuat. Terdapat banyak property di CSS e.g. `background-color`, `text-align`, dan lain-lain.

3. value, sebagai nilai dari property style nya e.g. `red` dapat menjadi value property `background-color`.

### Gaya Penulisan CSS

1. inline CSS, styling ditulis didalam element HTML menggunakan attribute style. E.g.

```html
<h1 style="color: red;">Halo dunia</h1>
```

2. internal CSS, styling ditulis didalam file HTML tetapi disendirikan didalam tag `<style></style>`. E.g.

```html
<style>
	h1 {
		color: red;
	}
</style>
```

3. external CSS, styling ditulis pada file terpisah dengan ekstensi file `.css`. Import file css menggunakan tag `<link>`. E.g.

![image](https://user-images.githubusercontent.com/73186952/192247093-16cca182-cc15-443f-8e4d-4581c26d824e.png)

Dari ketiga gaya penulisan tersebut akan menghasilkan output yang sama :<br />
![image](https://user-images.githubusercontent.com/73186952/192247977-fc7bc623-db4e-42a3-866c-cfa6fbfdf275.png)

## Algorithm

Algoritma merupakan deskripsi menggunakan tahapan-tahapan yang dibutuhkan untuk menyelesaikan suatu permasalahan. Dengan algoritma yang baik, hasil produk digital dapat memiliki waktu yang cepat dalam memproses serta memori yang kecil. Berikut contoh algoritma sederhana :

![image](https://user-images.githubusercontent.com/73186952/192252173-57aaf7cb-bb66-4eac-ae0a-31ec83279248.png)

### Jenis-Jenis Algoritma

1. Sequence, instruksi yang dijalankan secara berurutan.
2. Selection, instruksi dijalankan jika memenuhi suatu kondisi.
3. Iteration, instruksi yang dijalankan secara berulang jika memenuhi kondisi tertentu.
4. Concurrent, instruksi yang dijalankan secara bersamaan.

### Penyajian Algoritma

1. Deskriptif, penyajian algoritma dengan deskripsi tahapan-tahapan. E.g. :
   ![image](https://user-images.githubusercontent.com/73186952/192259417-a802b89b-73d9-492f-b8e1-ef6f83632e64.png)
2. Flowchart, penyajian algoritma yang direpresentasikan menggunakan **bangun datar** untuk setiap proses yang dilakukan. E.g. :
   ![image](https://user-images.githubusercontent.com/73186952/192259758-f17d8c16-b0f8-42ce-aeed-0617b1d38e76.png)
3. Pseudocode, penyajian algoritma yang hampir menyerupai penulisan kode program. E.g. :
   ![image](https://user-images.githubusercontent.com/73186952/192260095-9b50b865-cea8-46b2-a5f6-4e673403dd07.png)

## Javascript

# **Writing and Presentation Test Week 1**

---

## Unix Command Line

Command line adalah sebuah mekanisme untuk berinteraksi dengan sistem operasi atau perangkat lunak komputer. Sedangkan, CLI (command line interface) adalah antarmuka untuk menuliskan perintah-perintah tersebut. Contoh dari CLI seperti :

- bash
- cmd.exe
- dst

### Unix Command - Navigasi

#### **- pwd**

```bash
pwd
```

> `pwd` digunakan untuk menampilkan directory sedang digunakan.

#### **- ls**

```bash
ls
```

> `ls` digunakan untuk menampilkan isi dari directory yang sedang digunakan.

#### **- cd**

```bash
cd <dirpath>
```

> `cd` digunakan untuk berpindah directory.
> `dirpath` merupakan lokasi directory yang akan dituju.
> `dirpath` dapat relatif maupun absolut path.

### Unix Command - Manipulasi

#### **- touch**

```bash
touch <filename>
```

> `touch` digunakan untuk membuat sebuah file pada directory yang sedang digunakan.

> `filename` berisi nama file yang akan dibuat beserta ekstensinya.

#### **- mkdir**

```bash
mkdir <dirname>
```

> `mkdir` digunakan untuk membuat sebuah directory didalam directory yang sedang digunakan.

> `dirname` berisi nama directory yang akan dibuat.

#### **- cp**

```bash
cp <param1> <param2>
```

> `cp` digunakan untuk menyalin file/directory.

> `param1` berisi nama file atau nama directory.

> `param2` berisi nama directory yang akan menjadi tempat salinan.

> Khusus untuk menyalin directory tambahkan `-r` sebelum `param1`.

#### **- mv**

```bash
mv <param1> <param2>
```

> `mv` digunakan untuk memindahkan file.

> `mv` juga bisa digunakan untuk mengubah nama file.

> `param1` berisi nama file.

> `param2` berisi nama directory yang akan menjadi tempat salinan.

> `param2` dapat berisi nama file yang akan menjadi nama baru dari file pada `param1`.

#### **- rm**

```bash
rm <param1>
```

> `rm` digunakan untuk menghapus sebuah file/directory.

> `param1` berisi nama file atau nama directory.

> Khusus untuk menghapus directory tambahkan `-r` sebelum `param1`.

### Unix Command - Menampilkan Isi File

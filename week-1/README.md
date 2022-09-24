# **Writing and Presentation Test Week 1**

---

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

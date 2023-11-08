# Tipe Data

Tipe data merupakan pengklasifikasian data berdasarkan jenisnya. Pada JavaScript terdapat beberapa tipe data sebagai berikut:

## Undefined

Tipe data ini terbentuk ketika sebuah variabel tidak memiliki nilai. Artinya, ketika kita mendeklarasikan variabel tanpa menginisialisasikan nilainya, variabel tersebut menjadi undefined. Contoh:

```js
let nama;

console.log(typeOf(nama)); // undefined
```

## Number

Nilai dari tipe data number adalah angka. Variabel bertipe data number dituliskan seperti angka pada umumnya:

```js
const umur = 30;
```

Jika angka tersebut merupakan sebuah bilangan desimal, maka kita bisa gunakan tanda titik pada pecahan bilangannya.

```js
const phi = 3.14;
```

# String

String merupakan sebuah teks. Untuk menetapkan nilai pada String pada variabel, bisa menggunakan petik satu `('')`, petik dua `("")`, atau backtick ` (``) `

```js
const namaAwal = "Khoirul";
const tempatLahir = `Bekasi`;
```

# Boolean

Boolean hanya memiliki dua nilai, yaitu true atau false. Tipe data ini menjadi kunci utama dalam penentuan logika. Kita akan banyak menggunakannya nanti dalam materi if/else statement. Untuk menetapkan nilai boolean pada variabel, gunakan keyword true atau false seperti di bawah ini.

```js
const sudahMenikah = true;
const apakahHujan = false;
```

# Null

Tipe berikutnya adalah null. Serupa dengan undefined, namun null perlu diinisialisasikan pada variabel. Null biasa digunakan sebagai nilai sementara pada variabel, tapi sebenarnya nilai tersebut “tidak ada”.

```js
let isiDalamTas = null;
```

# Object

Object berisi pasangan key dan value yang juga dikenal dengan property. Key berperan mirip seperti nama variabel yang menyimpan sebuah nilai. Sementara, value berisi nilai dengan tipe data apa pun termasuk objek lain. Key dan value di dalam object dituliskan seperti berikut:

```js
const obj = {
  key1: "Value1",
  key2: "Value2",
};
```

Ketika kita mengubah object menggunakan assignment operator dan property/key-nya sudah ada, maka nilai di dalamnya akan tergantikan dengan nilai yang baru. Sedangkan, jika property dengan nama key yang ditentukan tidak ditemukan, maka property baru akan ditambahkan ke object.

```js
const orang = {
  nama: "Khoirul",
  umur: 25,
};

orang.umur = 30;
orang.sudahMenikah = true;
```

Kita juga dapat menghapus property pada object menggunakan keyword delete seperti berikut:

```js
const orang = {
  nama: "Khoirul",
  umur: 25,
};

delete orang.umur;
```

# Array

Array merupakan tipe data yang dapat mengelompokkan lebih dari satu nilai dan menempatkannya dalam satu variabel. Contoh:

```js
const arraySaya = [1, "dua", true];
```

Perbedaan array dengan object adalah data pada array disusun secara berurutan dan diakses menggunakan index. Untuk mengakses nilai di dalam array, kita gunakan tanda kurung siku [] yang di dalamnya berisi angka yang merupakan posisi nilai yang ingin diakses.

```js
console.log(arraySaya[1]); // dua
```

Untuk menambahkan isi array dari yang paling akhir, bisa menggunakan `push()`:

```js
arraySaya.push("data baru");

console.log(arraySaya); //[1, "dua", true, "data baru"]
```

Untuk menghapus isi array dari yang paling akhir, bisa menggunakan `pop()`:

```js
arraySaya.pop();

console.log(arraySaya); //[1, "dua", true]
```

Untuk menambahkan isi array dari yang paling awal, bisa menggunakan `unshift()`:

```js
arraySaya.unshift("data baru");

console.log(arraySaya); //["data baru", 1, "dua", true]
```

Untuk menghapus isi array dari yang paling awal, bisa menggunakan `shift()`:

```js
arraySaya.shift();

console.log(arraySaya); //[1, "dua", true]
```

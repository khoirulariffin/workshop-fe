# Variabel

Pada JavaScript setidaknya ada tiga cara untuk mendeklarasikan sebuah variabel, yaitu menggunakan keyword var, let, dan const. Pada versi ECMAScript 2015 (ES6) dikenalkan deklarasi variabel dengan let dan const untuk menggantikan var yang dinilai kontroversial dan rawan menimbulkan bug.

## var

Variabel `var` tidak memiliki cakupan blok (block scope), yang berarti variabel `var` akan tetap ada bahkan di luar blok kode.

```js
var nama = "Khoirul";
```

## let

Variabel `let` mempunyai cakupan blok (block scope). Ini berarti bahwa variabel `let` hanya dapat diakses di dalam blok di mana ia dideklarasikan, seperti dalam pernyataan kondisional.

Variabel `let` dapat diinisialisasi ulang, yang berarti Anda dapat mengubah nilainya setelah dideklarasikan.

```js
let nama = "Khoirul";
nama = "Ariffin";
```

## const

Variabel `const` juga memiliki cakupan blok (block scope), seperti let. Namun, variabel `const` harus diinisialisasi dengan nilai saat dideklarasikan, dan nilai variabel `const` tidak dapat diubah setelah dideklarasikan.

```js
const nama = "Khoirul";
nama = "Arif"; // ERROR!!
```

# Fungsi

Fungsi digunakan sebagai blok kode atau prosedur yang dapat digunakan secara berulang. Dalam arti lain, kita dapat berpikir bahwa function merupakan sebuah variabel yang berisi blok logika. Blok logika tersebut akan dieksekusi ketika dipanggil.

### Penulisan Fungsi

- Declaration Function

```js
function perkenalan() {
  console.log("Halo, nama saya Khoirul");
}

perkenalan(); // Halo, nama saya Khoirul
```

- Arrow Function

```js
const perkenalan = () => {
  console.log("Halo, nama saya Khoirul");
};

perkenalan(); // Halo, nama saya Khoirul
```

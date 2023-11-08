# Perulangan

Ketika menulis program komputer, akan ada situasi di mana kita perlu melakukan hal yang sama berkali-kali. Misalnya kita ingin menampilkan angka 1 sampai 5. Tentunya tidak praktis jika kita menulis kode seperti berikut:

```js
console.log(1);
console.log(2);
console.log(3);
console.log(4);
console.log(5);
```

# For Loop

Dari beberapa cara melakukan proses perulanggan pada JavaScript, “for” merupakan salah satu cara yang banyak digunakan. Struktur dasar dari for tampak seperti berikut:

```js
for(inisialisasi variabel; test kondisi; perubahan nilai variabel) {
  // lakukan sesuatu
}
```

```js
for (let i =1; i<=5; i++;){
    console.log(i);
}
```

# For...of

Cara lain dalam melakukan looping adalah menggunakan for..of. For of mulai hadir pada ECMAScript 2015 (ES6). Cara ini jauh lebih sederhana dan modern dibanding for loop biasa. Sintaks dasar dari for of loop adalah seperti ini:

```js
const myArray = ["Khoirul", "Ariffin", "Aiko"];
for (arrayItem of myArray) {
  console.log(arrayItem);
}
```

# Komponen

Komponen adalah suatu konsep dimana mengkapsulasi blok kode dari elemen HTML ke HTML tag baru

# Membuat Komponen

### Tambahkan File Baru di Dalam Folder <em>components</em>

- Klik kanan pada folder components
- `New File`, masukkan nama sesuai keinginan. Aturannya adalah dengan PascalCase dan 2 (dua) kata
- Akhiri dengan `.vue`

* dalam hal ini, saya membuat `PersegiBaru.vue`

### Buat Template SFC (Single-File Component)

```html
<template>
  <div></div>
</template>

<script setup></script>
```

Pastikan menggunakan `setup` pada `script` karena menggunakan `composition`. Dan tidak perlu `<style scoped>` karena kita menggunakan <u>`Tailwindcss`</u>

### Masukkan Sintaks di Bawah Ini Untuk Membuat Sebuah Persegi

```html
<template>
  <div class="h-40 w-40 bg-yellow-500 border rounded-md"></div>
</template>
```

karena kita hanya membuat persegi saja tanpa isi, kita bisa langsung menutup tag `div` tersebut

```html
<template>
  <div class="h-40 w-40 bg-yellow-500 border rounded-md" />
</template>
```

### Pakai Komponen Tersebut

- Pada target halaman (dalam hal ini `app.vue`), import komponen yang telah dibuat

```html
<script setup>
  import PersegiBaru from "@/components/PersegiBaru.vue";
</script>
```

- Panggil Komponen tersebut, sehingga sintaks lengkapnya seperti di bawah ini:

```html
<template>
  <div class="flex h-screen w-screen justify-center items-center">
    <PersegiBaru />
  </div>
</template>

<script setup>
  import PersegiBaru from "@/components/PersegiBaru.vue";
</script>
```

### Kustomisasi Properti Pada Komponen

Kita bisa kustom properti pada komponen dengan menggunakan `props`

- Pada file `PersegiBaru.vue` definisikan props yang berisikan warna yang memiliki warna bawaan kuning

```html
<script setup>
  const props = defineProps({
    warna: {
      default: "bg-yellow-500",
    },
  });
</script>
```

- Masih pada file `PersegiBaru.vue`, ubah `class` pada `div` persegi tersebut menjadi binding. Bisa dengan `v-bind:class` atau `:class`
- Tambahkan kondisi, ketika warna terisi, ia akan memakai warna tersebut. Jika tidak, ia akan memakai warna default. Sehingga sintaks lengkapnya akan seperti berikut:

```html
<template>
  <div :class="`h-40 w-40 border rounded-md ${props.warna}`" />
</template>

<script setup>
  const props = defineProps({
    warna: {
      default: "bg-yellow-500",
    },
  });
</script>
```

- Kemudian lihat, apakah komponen PersegiBaru tadi ada perubahan? Tentu saja tidak. Tetap berwarna kuning, karena kita tidak mengirim warna ketika komponen dipanggil

#### Mengirim Warna Dari <em>Parent</em> ke Komponen

- Masuk ke dalam file `app.vue`
- Tambahkan properti `warna` pada kompenen PersegiBaru

```html
<PersegiBaru warna="bg-red-500" />
```

- Apakah warnanya berganti?

## Menambahkan Aksi pada Komponen yang Berasal dari <em>Parent</em>

Adakalanya kita membuat suatu komponen yang dapat digunakan kembali, namun aksinya berasal dari parent. Seperti `button`. Biasanya kita tidak menulis logika ketika diklik pada button tersebut, kan? Namun pada halaman yang memanggilnya.

Berikut caranya:

- Pada `PersegiBaru.vue` Definisikan sebuah `emit` yang bernama `onClick` (bebas, tidak masalah)

```js
const emit = defineEmits(["onClick"]);
```

- Buat sebuah fungsi untuk menangani proses klik tersebut, yang didalamnya memanggil emit tersebut

```js
const handleClick = () => {
  emit("onClick");
};
```

- Tambahkan `event` click pada persegi tersebut dengan `v-on` atau `@`. Kemudian panggil fungsi yang kita buat sebelumnya

- Pada `app.vue`, buat suatu fungsi yang kita butuhkan. Contohnya, saya membuat 2 (dua) fungsi yang dimana mengeluarkan sebuah `alert` yang bertuliskan `klik pertama` dan `klik kedua`

```js
const klikPertama = () => {
  alert("klik pertama");
};

const klikKedua = () => {
  alert("klik kedua");
};
```

- Kirim fungsi tersebut ke komponen dengan pancaran (emit) yang telah kita buat sebelumnya, yang bernama `onClick`. Kirimnya menggunakan `v-on` atau `@`. Berikut sintaks lengkapnya:

```html
<template>
  <div class="flex h-screen w-screen justify-center items-center gap-20">
    <PersegiBaru warna="bg-red-500" @onClick="klikPertama" />
    <PersegiBaru warna="bg-purple-500" @onClick="klikKedua" />
  </div>
</template>

<script setup>
  import PersegiBaru from "@/components/PersegiBaru.vue";

  const klikPertama = () => {
    alert("klik pertama");
  };

  const klikKedua = () => {
    alert("klik kedua");
  };
</script>
```

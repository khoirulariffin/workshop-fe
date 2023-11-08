# Fetch Data

Ketika membuat suatu website atau aplikasi, seringkali kita membutuhkan data pihak luar yang biasa disebut <em>Consume API</em>

# AXIOS

Axios adalah suatu libarary atau pustaka yang berfungsi untuk menangani permintaan HTTP (<em>HTTP Request</em>)

## Instalasi

```
npm i axios
```

## Pemakaian

- Pada file `app.vue`, di bagian `script`, import axios

```js
import axios from "axios";
```

- Buat suatu variabel reactive menggunakan `ref` yang memiliki nilai awal `null`

```js
const cars = ref(null);
```

- Buat suatu fungsi untuk fetching data dengan axios, yang dimana hasil fetch data tersebut dimasukkan ke dalam variabel sebelumnya (`cars`)

```js
const fetchData = async () => {
  const { data } = await axios.get("/cars_data.json");
  cars.value = data;
};
```

- Masukkan fungsi tersebut ke dalam salah satu persegi yang telah dibuat sebelumnya

```html
<PersegiBaru warna="bg-purple-500" @onClick="fetchData" />
```

- Buat tag html baru untuk menampilkan hasil fetch. Buat kondisi ketika data tersebut tidak ada, maka tag tersebut tidak tampil

```html
<p v-if="Array.isArray(cars) && cars.length !== 0">{{ cars }}</p>
```

- Berikut sintaks lengkapnya:

```html
<template>
  <div
    class="flex flex-col h-screen w-screen justify-center items-center gap-20"
  >
    <PersegiBaru warna="bg-red-500" @onClick="klikPertama" />
    <PersegiBaru warna="bg-purple-500" @onClick="fetchData" />
    <p v-if="Array.isArray(cars) && cars.length !== 0">{{ cars }}</p>
  </div>
</template>

<script setup>
  import axios from "axios";

  import { ref } from "vue";

  import PersegiBaru from "@/components/PersegiBaru.vue";

  const cars = ref(null);

  const klikPertama = () => {
    alert("klik pertama");
  };

  const fetchData = async () => {
    const { data } = await axios.get("/cars_data.json");
    cars.value = data;
  };
</script>
```

## Bagaimana Jika Ingin Fetch Tanpa Trigger Tombol?

- Pada `app.vue`, tambahkan import `onMounted` dari `vue`

```js
import { onMounted } from "vue";
```

- Deklarasikan `onMounted`, lalu panggil `fetchData()`

```js
onMounted(() => {
  fetchData();
});
```

- Berikut sintaks lengkapnya:

```html
<template>
  <div
    class="flex flex-col h-screen w-screen justify-center items-center gap-20"
  >
    <PersegiBaru warna="bg-red-500" @onClick="klikPertama" />
    <PersegiBaru warna="bg-purple-500" @onClick="fetchData" />
    <p v-if="Array.isArray(cars) && cars.length !== 0">{{ cars }}</p>
  </div>
</template>

<script setup>
  import axios from "axios";

  import { ref, onMounted } from "vue";

  import PersegiBaru from "@/components/PersegiBaru.vue";

  const cars = ref(null);

  const klikPertama = () => {
    alert("klik pertama");
  };

  const fetchData = async () => {
    const { data } = await axios.get("/cars_data.json");
    cars.value = data;
  };

  onMounted(() => {
    fetchData();
  });
</script>
```

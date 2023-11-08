# Directives

Adalah fitur dari Vuejs yang memudahkan kita untuk menambahkan atau memberikan perilaku khusus untuk komponen HTML

## v-text

`v-text` akan menampilkan teks biasa bertipe string pada konten HTML

```html
<template>
  <div>
    <h1 v-text="nama"></h1>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const nama = ref("khoirul");
</script>
```

Bisa juga menggunakan text interpolation:

```html
<h1>{{ nama }}</h1>
```

## v-html

`v-html` akan menampilkan konten murni HTML

```html
<template>
  <div>
    <h1 v-html="namaHTML"></h1>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const namaHTML = ref("<p>khoirul</p>");
</script>
```

## v-if & v-else

`v-if` akan menampilkan blok yang diberikan kondisi jika bernilai true

`v-else` akan menampilkan ketika blok yang diberikan bernilai selain kondisi `v-if` terpenuhi

```html
<template>
  <div>
    <h1 v-if="isMarriage">Sudah Menikah</h1>
    <h1 v-else>Belum Menikah</h1>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const isMarriage = ref(false);
</script>
```

## v-else-if

`v-else-if` sama seperti `if`, akan menampilkan blok yang diberikan kondisi bernilai true. Namun bergantung kepada `if`. Jika `if` sudah true, maka `else-if` tidak tampil

```html
<template>
  <div>
    <h1 v-if="tipe === 'A'">Masuk A</h1>
    <h1 v-else-if="tipe === 'B'">Masuk B</h1>
    <h1 v-else>Tidak Masuk A maupun B</h1>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const tipe = ref("B");
</script>
```

## v-for

`v-for` akan menampilkan blok sebanyak panjang dari target

```html
<template>
  <div>
    <h1 v-for="type in types" :key="type">{{ type }}</h1>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const types = ref(["A", "B", "C", "D"]);
</script>
```

## v-on

`v-on` menambahkan `event` atau aksi pada blok yang ditandai

```html
<template>
  <div>
    <button v-on:click="clickMe">Tekan aku</button>
  </div>
</template>

<script setup>
  const clickMe = () => {
    alert("Tertekan!");
  };
</script>
```

bisa juga dengan shorthand atau disingkan menjadi:

```html
<button @click="clickMe">Tekan aku</button>
```

## v-bind

`v-bind` berfungsi untuk mendinamiskan suatu atribut

```html
<template>
  <div>
    <button v-bind:class="status === true ? 'bg-blue-500' : 'bg-yellow-300'">
      Tekan aku
    </button>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const status = ref(false);
</script>
```

bisa juga dengan shorthand menjadi:

```html
<template>
  <div>
    <button :class="status === true ? 'bg-blue-500' : 'bg-yellow-300'">
      Tekan aku
    </button>
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const status = ref(false);
</script>
```

## v-model

`v-model` berfungsi untuk mengikat suatu nilai ke dalam suatu komponen, biasanya adalah komponen input seperti `text field`

```html
<template>
  <div class="flex flex-col">
    {{ inputan }}
    <input type="text" v-model="inputan" />
  </div>
</template>

<script setup>
  import { ref } from "vue";

  const inputan = ref("");
</script>
```

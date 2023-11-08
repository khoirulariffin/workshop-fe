# Visualisasi Bagan atau Chart

Dalam praktiknya, menampilkan suatu data, tidak hanya dalam sebuah teks utuh. Beberapa kasus, perlu menggunakan bagan atau chart untuk visualisasinya

## Instalasi Chartjs

https://www.chartjs.org/
https://github.com/apertureless/vue-chartjs/

```js
npm i vue-chartjs chart.js

```

## Pembuatan Komponen Chart

- Buat file baru pada folder `components`, dalam hal ini saya membuat `BarChart.vue` karena ingin membuat BarChart
- Buat template kosong, tidak perlu `style scoped`

```html
<template>
  <div></div>
</template>

<script setup></script>
```

- Import wajib:

```js
import {
  Chart as ChartJS,
  Title,
  Tooltip,
  Legend,
  BarElement,
  CategoryScale,
  LinearScale,
} from "chart.js";
```

- Import tipe chartnya, dalam hal ini saya memakai Bar

```js
import { Bar } from "vue-chartjs";
```

- Registerkan hasil import yang pertama

`ChartJS.register(CategoryScale, LinearScale, BarElement, Title, Tooltip, Legend)`

- Karena dalam Chart butuh data dan pengaturannya, maka kita props yang akan nanti diterima. Props ini wajib, dan bertipe objek

```js
const props = defineProps({
  data: {
    type: Object,
    required: true,
  },
  options: {
    type: Object,
    required: true,
  },
});
```

- Panggil `Bar` yang sudah diimport ke blok `<template>`. Bar tersebut secara bawaan atau default, menerima `data` dan `options` juga. Maka dari itu, mari kita kirim kan

```html
<Bar :data="props.data" :options="props.options" />
```

## Pemakaian Komponen Chart

- Pada `app.vue`, buat variabel reaktif yang bernama `data` bertipe objek. `data` tersebut berisikan `labels` yang memiliki nilai array berisi string bulan `Januari` sampai `Maret`.
- Selain `labels`, tambahkan juga properti `datasets` bertipe array yang berisi objek dan memiliki properti data bernilai `40, 20, 12` dan properti backgroundColor bernilai `'#45322E', '#4C9141', '#497E76'`. Berikut sintaksnya:

```js
const data = ref({
  labels: ["January", "February", "March"],
  datasets: [
    { data: [40, 20, 12], backgroundColor: ["#45322E", "#4C9141", "#497E76"] },
  ],
});
```

- Kemudian buat juga variabel reaktif bernama `options` yang berisi objek dan memiliki properti `responsive` bernilai `true`

```js
const options = ref({
  responsive: true,
});
```

- Import komponen yang kita buat:

```js
import BarChart from "@/components/BarChart.vue";
```

- Panggil dan kirim variabel `data` dan `options` yang kita buat tadi ke dalam komponen

```html
<BarChart :data="data" :options="options" />
```

- Dan berikut sintaks lengkapnya

```html
<template>
  <div
    class="flex flex-col h-screen w-screen justify-center items-center gap-20"
  >
    <div class="h-[40vh] w-[40vw] overflow-hidden">
      <BarChart :data="data" :options="options" />
    </div>
    {{ cars }}
  </div>
</template>

<script setup>
  import axios from "axios";

  import { ref, onMounted } from "vue";

  import BarChart from "@/components/BarChart.vue";

  const cars = ref(null);

  const data = ref({
    labels: ["January", "February", "March"],
    datasets: [
      {
        data: [40, 20, 12],
        backgroundColor: ["#45322E", "#4C9141", "#497E76"],
      },
    ],
  });
  const options = ref({
    responsive: true,
  });

  const fetchData = async () => {
    const { data } = await axios.get("/cars_data.json");
    cars.value = data;
  };

  onMounted(() => {
    fetchData();
  });
</script>
```

# Bagaimana Mengganti Data Statis Menjadi Data Hasil Fetch?

- Buat variabel reaktif baru bernama newData dengan nilai null
- Pada fungsi fetchData, hapus reassign `cars.value`
- Buat variabel baru bernama rawLabels yang berisi hasil mapping `data` yang kita fetch, ambil brand-nya saja
- Buat variabel baru bernama rawSales yang berisi hasil mapping `data` yang kita fetch, ambil sales-nya saja
- Reassign newData.value menjadi sebuah objek dimana memiliki properti labels yang berisi rawLabels dan datasets berisi array yang berisi sebuah objek yang memiliki properti data bernilai rawSales
- Berikut sintaks lengkapnya:

```js
const fetchData = async () => {
  const { data } = await axios.get("/cars_data.json");

  const rawLabels = data.map((e) => e.brand);
  const rawSales = data.map((e) => e.sales);

  newData.value = {
    labels: rawLabels,
    datasets: [{ data: rawSales }],
  };
};
```

- Pada `BarChart` yang kita panggil di atas, tambahkan kondisi dengan `v-if`: Ia akan tampil jika newData tidak kosong
- pada props data (`:data`) ubah yang tadinya `data`, menjadi `newData`

```html
<BarChart v-if="newData" :data="newData" :options="options" />
```

- Berikut sintaks lengkapnya:

```html
<template>
  <div
    class="flex flex-col h-screen w-screen justify-center items-center gap-20"
  >
    <div class="h-[80vh] w-[80vw] overflow-hidden">
      <BarChart v-if="newData" :data="newData" :options="options" />
    </div>
  </div>
</template>

<script setup>
  import axios from "axios";

  import { ref, onMounted } from "vue";

  import BarChart from "@/components/BarChart.vue";

  // const cars = ref(null)

  const newData = ref(null);

  // const data = ref({
  //   labels: ['January', 'February', 'March'],
  //   datasets: [{ data: [40, 20, 12], backgroundColor: ['#45322E', '#4C9141', '#497E76'] }]
  // })
  const options = ref({
    responsive: true,
    plugins: {
      legend: {
        display: false,
      },
    },
  });

  const fetchData = async () => {
    const { data } = await axios.get("/cars_data.json");

    const rawLabels = data.map((e) => e.brand);
    const rawSales = data.map((e) => e.sales);

    newData.value = {
      labels: rawLabels,
      datasets: [{ data: rawSales }],
    };
  };

  onMounted(() => {
    fetchData();
  });
</script>
```

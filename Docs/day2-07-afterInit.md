# Instalasi Tailwindcss pada VueJs

Pada `tailwind.config.js` tambahkan sintaks berikut pada `content`:

```
content: [
    "./index.html",
    "./src/**/*.{vue,js,ts,jsx,tsx}",
  ],
```

Pada `main.css` yang terletak di folder `src -> assets`, hapus semua sintaksnya dan ganti dengan:

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

Hapus `base.css`

# Susunan Folder

Ketika pertama kali membuka projek, pasti banyak folder dan files. Mari kita bahas:

### node_modules

Berisikan modul-modul yang sudah kita instal sebelumnya

### public

Secara bawaan, public berisikan file icon untuk judul pada tab browser. Namun kita juga bisa menambahkan dummy file json untuk fetch data

### src

src berisikan semua kebutuhan pengembangan web kita

### src -> assets

Folder `assets` berisikan file css, icon, gambar, dan file pendukung lainnya yang akan kita gunakan

### src -> components

Folder `components` berisikan semua komponen yang akan kita pakai seperti Button, Chart, dan sebagainya

### src -> router

Folder `router` berisikan alamat semua halaman pada website beserta konfigurasinya

### src -> stores

Folder `stores` berisikan file state manajemen atau manajemen variabel global (contoh: `userStore.js`, `bookStore.js`)

### src -> views

Folder `views` berisikan file halaman yang ada pada website (contoh: `HomeView.vue`)

### app.vue

Berisikan sintaks SFC yang bebas digunakan

### main.js

Berisikan pemakaian third-party dependencies yang akan di masukkan (mount) pada aplikasi atau web

### index.html

Berisikan file html yang menjadi dasar atau root untuk aplikasi atau web

# Tailwindcss

Tailwind CSS adalah sebuah framework CSS yang dirancang untuk mempermudah pembuatan tampilan web dengan pendekatan utility-first.

# Instalasi

### Pastikan Projek Sudah Terinisialisasi

- Apakah sudah ada file package.json?
- Jika belum, jalankan perintah `npm init` lalu isi semua pertanyaan
- Jika ingin melewati semua pertanyaan, ubah perintah pertama menjadi `npm init -y`

### Jalankan Perintah untuk Instalasi Tailwindcss

```
npm install -D tailwindcss && npx tailwindcss init
```

Pada `tailwind.config.js`, tambahkan `content: ["./src/**/*.{html,js}"],` yang berarti Tailwindcss akan membaca pada folder src berserta seluruh subfolder dan semua berkas di dalamnya yang berekstensi `.html` dan `.js`

Jika folder atau berkas yang dituju berbeda, silakan bisa disesuaikan.

### Tambahkan Tailwind Directives pada Berkas CSS

Dalam hal ini, berkas CSS kita ada di folder `styles`

```
@tailwind base;
@tailwind components;
@tailwind utilities;
```

### Jalankan Tailwind CLI Build Process

`npx tailwindcss -i ./styles/input.css -o ./styles/style.css --watch`

# Pemakaian

```html
<h1 class="font-bold text-black/80">LANDING</h1>
```

Teks <em>header</em> tersebut memiliki ketebalan Bold dan berwarna Hitam yang transparansi warnanya 80%

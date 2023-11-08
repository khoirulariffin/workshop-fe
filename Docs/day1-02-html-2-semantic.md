# Semantic HTML: Penggunaan Elemen dari `<header>` hingga `<footer>`

HTML5 menawarkan sejumlah elemen semantik yang dirancang untuk meningkatkan struktur dan pemahaman konten pada halaman web. Elemen-elemen ini membantu peramban dan mesin pencari untuk memahami peran dan hubungan berbagai bagian dalam halaman web Anda.

## `<header>`

Elemen `<header>` digunakan untuk menandai bagian atas halaman atau bagian paling atas dari sebuah elemen konten tertentu. Ini biasanya berisi elemen-elemen seperti judul halaman, logo, dan tautan navigasi utama. Contoh penggunaan:

```html
<header>
  <h1>Halaman Utama</h1>
  <nav>
    <ul>
      <li><a href="/">Beranda</a></li>
      <li><a href="/tentang">Tentang Kami</a></li>
      <li><a href="/layanan">Layanan</a></li>
    </ul>
  </nav>
</header>
```

## `<nav>`

Elemen `<nav>` digunakan untuk menandai blok tautan navigasi di dalam halaman. Ini membantu dalam mengidentifikasi tautan-tautan yang mengarah ke bagian-bagian berbeda dari situs web. Contoh penggunaan:

```html
<nav>
  <ul>
    <li><a href="/">Beranda</a></li>
    <li><a href="/tentang">Tentang Kami</a></li>
    <li><a href="/layanan">Layanan</a></li>
  </ul>
</nav>
```

## `<main>`

Elemen `<main>` digunakan untuk menandai konten utama dari halaman web, yang biasanya berisi informasi atau konten utama yang ingin disampaikan kepada pengguna. Contoh penggunaan:

```html
<main>
  <h2>Selamat datang di Situs Kami!</h2>
  <p>Kami adalah perusahaan yang berfokus pada pengembangan solusi web.</p>
  <p>Jelajahi layanan kami dan temukan apa yang kami tawarkan!</p>
</main>
```

## `<section>`

Elemen `<section>` digunakan untuk mengidentifikasi bagian atau bagian dari konten yang memiliki hubungan tematik atau topik yang serupa. Contoh penggunaan:

```html
<section>
  <h2>Bagian 1</h2>
  <p>Ini adalah isi dari Bagian 1.</p>
</section>
<section>
  <h2>Bagian 2</h2>
  <p>Ini adalah isi dari Bagian 2.</p>
</section>
```

## `<article>`

Elemen `<article>` digunakan untuk mengelompokkan konten yang berdiri sendiri, seperti posting blog, berita, atau cerita. Ini membantu dalam pengenalan konten yang dapat berdiri sendiri. Contoh penggunaan:

```html
<article>
  <h3>5 Tips untuk Pengembangan Web yang Sukses</h3>
  <p>
    Di artikel ini, kami akan memberikan tips dan panduan untuk pengembangan web
    yang sukses.
  </p>
  <p>Tips pertama adalah...</p>
</article>
```

## `<footer>`

Elemen `<footer>` digunakan untuk menandai bagian bawah halaman yang biasanya berisi informasi tambahan seperti informasi kontak, tautan ke halaman terkait, atau hak cipta. Contoh penggunaan:

```html
<footer>
  <p>&copy; 2023 Nama Perusahaan</p>
  <p>Kontak: info@namaperusahaan.com</p>
</footer>
```

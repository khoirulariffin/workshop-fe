# CSS (Cascading Style Sheets)

CSS (Cascading Style Sheets) adalah bahasa stylesheet yang digunakan untuk mengontrol tampilan dan tata letak elemen-elemen HTML pada halaman web. CSS memungkinkan Anda untuk memisahkan struktur (HTML) dari tampilan (desain) sebuah situs web.

## Menuliskan Aturan Styling

1. Pilih elemen HTML yang akan diubah tampilannya dengan menggunakan selector, seperti tag HTML, kelas, ataupun ID.
1. Berikan deklarasinya.

Contoh:

```css
p {
  color: blue;
}
.paragraf {
  background-color: red;
}
#paragraf2 {
  padding: 10px;
}
```

| Selector            | Property         | Value |
| ------------------- | ---------------- | ----- |
| `p` (tag)           | color            | blue  |
| `.paragraf` (class) | background-color | red   |
| `#paragraf2` (ID)   | padding          | 10px  |

## Penerapan Styling pada Dokumen HTML

### Inline Style

```html
<p style="font-weight: bold; color: green;">
  Teks ini tebal dan berwarna hijau.
</p>
```

### Embedded Style Sheet

```html
<body>
  ...

  <style>
    p {
      color: purple; /* paragraf tersebut berwarna ungu */
    }
  </style>
</body>
```

### External Style Sheet

Merupakan berkas terpisah yang di dalamnya hanya terdapat sebuah aturan atau deklarasi CSS. Berkas ini harus berekstensi .css, dan berkas ini nantinya dihubungkan pada dokumen HTML.

Untuk menyambungkan berkas .css dengan dokumen HTML, kita dapat menggunakan elemen `<link>` pada `<head>` berkas HTML. Contohnya:

```html
<head>
  <title>Personal Website</title>
  <link rel="stylesheet" type="text/css" href="style.css" />
</head>
```

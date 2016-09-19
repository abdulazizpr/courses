<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Membangun Halaman Web Pertama

---
<!-- page_number: true -->
<!-- *template: invert -->
## Apa itu HTML & CSS?

---

**HTML**, **H**yper<b>T</b>ext **M**arkup **L**anguage, mengatur struktur konten dan memberikan arti pada konten tersebut sebagai, misalkan, heading, paragraf, atau gambar.

**CSS**, **C**ascading **S**tyle **S**heets, mengatur tampilan dari konten, misalnya, font atau warnanya.

> HTML dan CSS sebaiknya berada pada file yang terpisah

---
<!-- *template: invert -->
## Istilah Dasar HTML

---

### Tag

Tag terdiri dari kurung lancip buka `<`, nama tagnya dan kurung lancip tutup `>`. 

**Contoh**:
``` html
<a>
```

---

### Elemen

Elemen terdiri dari tag pembuka, konten dan tag penutup. Tag penutup adalah tag yang diberi tanda garis miring kanan `/` sebelum nama tag.

**Contoh**:
``` html
<a> ... </a>
```

---

## Atribut

Atribut adalah informasi tambahan dari elemen. Atribut ditulis dalam tag pembuka setelah nama tag. 

**Contoh**:
``` html
<a href="http://makersinstitute.co.id/">Makers Institute</a>
```

**Hasil**:
<object data="https://gitlab.com/danieljuvito/html-css/blob/master/html-css/hasil/hasil-1-1/index.html" width="860px" height="60px"> <embed src="https://gitlab.com/danieljuvito/html-css/blob/master/html-css/hasil/hasil-1-1/index.html" width="860px" height="60px"> Error: Embedded data could not be displayed. </object>

---

<!-- *template: invert -->
## Struktur Dokumen

---

Dokumen HTML disimpan dengan ekstensi `.html`. 

Untuk menulis HTML, kita gunakan text editor seperti: 
* **Notepad** (Win) 
* **TextEdit** (Mac)

Semua dokumen HTML memiliki struktur dasar yang mencakup elemen: 
* `<!DOCTYPE html>`
* `<html>`
* `<head>`
* `<body>`.

---

### Tag `<!DOCTYPE html>`

Deklarasi tipe dokumen, atau `<!DOCTYPE html>`, memberitahu browser bahwa HTML versi 5 yang kita gunakan. 

<br>

> Kita dapat menggunakan versi yang lain, namun deklarasinya berbeda dan lebih panjang.

---

### Elemen `<html>`

Elemen HTML dapat bersarang, atau berada dalam elemen yang lain.

Semua elemen HTML harus berada di dalam elemen `<html>`.

---

### Elemen `<head>`

Elemen `<head>` berisi metadata (informasi tentang halamannya), seperti: 
* Judul dokumen (ditampilkan pada title bar pada browser)
* Link ke file eksternal
* Dll 

Konten di dalam elemen `<head>` tidak akan ditampilkan.

---

### Elemen `<body>`

Semua elemen yang dapat ditampilkan ke layar harus berada di dalam elemen `<body>`, seperti:
* Link
* Paragraf
* Heading
* Gambar
* Dll

---

**Contoh**:
``` html
<!DOCTYPE html>
<html lang="en">
  <head>
    <meta charset="utf-8">
    <title>Halo Dunia</title>
  </head>
  <body>
    <h1>Halo Dunia</h1>
    <p>Ini adalah halaman web.</p>
  </body>
</html>
```

> Tag `<meta charset="utf-8">` dalam elemen `<head>` memberitahu browser karakter yang kita gunakan.

---

**Hasil**:
<object data="C:\makersinstitute\slide\1-html-css\1-halaman-web-pertama\hasil-2\index.html" width="860px" height="140px"> <embed src="C:\makersinstitute\slide\1-html-css\1-halaman-web-pertama\hasil-2\index.html" width="860px" height="140px"> Error: Embedded data could not be displayed. </object>

---

#### Elemen tanpa Tag Penutup

Ada beberapa elemen yang tidak perlu tag penutup. Konten yang diperlukan berasal dari atributnya saja. Salah satu contohnya yaitu elemen `<meta>`. Kontennya berasal dari atribut `charset`. Berikut beberapa contoh elemen tanpa tag penutup.

* `<br>`
* `<img>`
* `<meta>`
* `<wbr>`
* `<embed>`
* `<input>`
* `<param>`
* `<hr>`
* `<link>`
* `<source>`

---

#### Validasi Kode

W3C mempunyai validator HTML dan CSS untuk memeriksa kesalahan, sehingga kode kita dapat dijalankan untuk semua browser dan melatih kita untuk menulis kode dengan baik.

---

<!-- *template: invert -->
## Istilah Dasar CSS

---

## Selektor

Selektor digunakan untuk memilih elemen HTML yang akan diberi style. Setelah selektor diikuti dengan tanda kurung kurawal buka `{` dan tutup `}`. 

**Contoh**:
``` css
p { ... }
```

---

### Properti

Properti yang ingin dihias ditulis di dalam kurung kurawal `{` dan `}`, dan diikuti dengan tanda titik dua `:`. 

**Contoh**:
``` css
p {
  color: ...
  font-size: ...
}
```

---

### Nilai

Setiap properti dapat kita beri nilai yang bersesuaian, yang ditulis setelah tanda titik dua `:` dan diakhiri dengan tanda titik-koma `;`. 

**Contoh**:
``` css
p {
  color: orange;
  font-size: 16px;
}
```
Kode ini akan memilih semua elemen `<p>`, mengubah warna tulisannya menjadi jingga, dan mengubah ukuran hurufnya menjadi 16 pixel.

---

<!-- *template: invert -->
## Bekerja Dengan Selektor

---

### Selektor Tipe

Selektor tipe memilih elemen dari tipe elemennya. Contohnya jika kita ingin memilih semua elemen `<div>` maka kita gunakan selektor `div`.

**CSS**:
``` css
div { ... }
```

**HTML**:
``` html
<div> ... </div>
<div> ... </div>
```

---

### Selektor Class

Selektor Class memilih elemen berdasarkan atribut `class` dari elemen. Nilai dari atribut `class` dapat digunakan pada lebih dari 1 elemen dan pada tipe elemen yang berbeda. Selektornya yaitu tanda titik `.` kemudian diikuti dengan nilai dari atribut `class`.

**CSS**:
``` css
.keren { ... }
```

**HTML**:
``` html
<div class="keren"> ... </div>
<p class="keren"> ... </p>
```

---

### Selektor ID

Selektor ID lebih spesifik dari selektor class, yaitu hanya memilih elemen berdasarkan atribut `id`. Berbeda dengan `class`, dua elemen tidak dapat memiliki nilai atibut `id` yang sama. Selektornya yaitu tanda pagar `#` diikuti dengan nilai dari atribut `id`.

**CSS**:
``` css
#danieljuvito { ... }
```

**HTML**:
``` html
<div id="danieljuvito"> ... </div>
```

---

<!-- *template: invert -->
## Merujuk CSS

---

File CSS memiliki ekstensi `.css` dan kita simpan satu folder dengan file HTML kita atau berada dalam subfolder.

Agar CSS dapat memberi style pada file HTML kita, maka file CSS tersebut harus dirujuk. Rujukannya kita simpan dalam elemen `<head>`.

Elemen `<link>` digunakan untuk merujuk file yang lain. Karena yang dirujuk adalah file CSS maka kita spesifikan atribut `rel` menjadi `stylesheet`. Atribut `href` digunakan menentukan lokasi dari file CSS tersebut.

---

**Contoh**:
```html
<head>
  <link rel="stylesheet" href="main.css">
</head>
```

> Jika file CSS kita berada dalam subfolder `stylesheets` maka nilai dari atribut href haruslah `stylesheets/main.css`.

---

<!-- *template: invert -->
## Menggunakan CSS Reset

---

Setiap browser mempunyai style default-nya. Untuk memastikan bahwa style yang kita gunakan dapat berjalan pada semua browser, maka CSS reset digunakan untuk me-reset semua style yang ada, seperti warna, margin, padding, ukuran, dan lain-lain.

Karena sifat CSS yang kaskade maka CSS reset harus kita rujuk pertama kali.

Ada beberapa jenis reset yang tersedia. Salah satu yang populer adalah [Eric Meyer's reset](http://meyerweb.com/eric/tools/css/reset/), yang sudah meliputi elemen HTML5.

---

## Rangkuman

Hal yang sudah dipelajari: 
* Perbedaan antara **HTML** dan **CSS**
* Berkenalan dengan **tag**, **elemen**, dan **atribut** dari HTML
* Menyusun **struktur** pada halaman web pertama.
* Berkenalan dengan **selektor**, **properti**, dan **nilai** dari CSS
* **Merujuk** CSS pada HTML
* Nilai dari **CSS reset**
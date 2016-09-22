<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Bekerja dengan Tipografi

**Outline:**
* [Memberi Warna pada Teks](#1)
* [Mengubah Properti Font](#2)
* [Menerapkan Properti Text](#3)
* [Menyisipkan Font Web](#4)
* [Memuat Rujukan &amp; Kuotasi](#5)

<hr>

###### Typeface vs. Font

Istilah typeface dan font sering tertukar, dan menimbulkan kebingungan.

Typeface adalah apa yang kita lihat. Tentang impresi artistik dari melihat, merasakan dan membaca teks.

Sedangkan font adalah file yang memuat typeface. Dengan menggunakan font pada computer maka komputer dapat mengakses typeface.

Untuk mempermudah penjelasan, bandingkan dengan lagu dan MP3. Typeface mirip dengan lagu, yang merupakan hasil karya seni. Sedangkan font mirip dengan MP3, bukan hasil karya seni tetapi sebuah metode untuk menyalurkan hasil karya seni.

<hr>

## Memberi Warna pada Teks <a name="1"></a>

Salah satu keputusan yang pertama kali harus diambil adalah memilih typeface dan warnanya.

Satu-satunya properti untuk memilih warna tulisan adalah properti `color`. Properti `color` meneriman satu nilai warna tapi dalam berbagai format seperti: hexadesimal, RGB, RGBa, HSL, dan HSLa. Hexadesimal merupakan nilai yang paling sering digunakan.

Berikut CSS yang mengubah warna semua teks di dalam elemen `<html>`:

``` css
html {
  color: #555;
}
```

## Mengubah Properti Font <a name="2"></a>

CSS menawarkan banyak properti berbeda untuk mengedit tampilan dari tulisan pada halaman. Properti ini terbagi menjadi dua kategori: properti berdasarkan font dan properti berdasarkan tulisan. Properti ini memiliki kode `face-*` dan `text-*`.

### Properti `font-family`

Properti `font-family` digunakan untuk memilih font dan memilih cadangan font yang akan ditampilkan. Nilai dari properti `font-family` mengandung nama-nama font yang dipisahkan dengan koma.

Font yang pertama kali dideklarasi, yang paling kiri, adalah font utama. Jika font utama ini tidak tersedia maka alternatif harus dideklarasikan setelahnya di sebelah kanannya.

Nama font yang terdiri dari lebih dari dua huruf harus dibungkus dengan tanda kutip `" "`. Font yang terakhir haruslah nilai kata kunci, merupakan font default dari sistem. Biasanya `sans-serif` atau `serif`.

``` css
body {
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```
Pada kasus ini, `Helvetica Neue` merupakan font yang akan digunakan. Jika font ini tidak tersedia, maka font selanjutnya yang akan digunakan, yaitu `Helvetica`, dan setertusnya.

### Properti `font-size`

Properti `font-size` digunakan untuk mengubah ukutan tulisan seperti: pixel, satuan em, persentase, titik, dan kata kunci `font-size`.

``` css
body {
  font-size: 14px;
}
```

### Properti `font-style`

Untuk mengubah tulisan menjadi cetak miring, atau membuat tulisan menjadi tidak dapat dicetak miring, kita gunakan properti `font-style`. Properti `font-style` menerima empat kata kunci: `normal`, `italic`, `oblique`, dan `inherit`. Dari keempat kata kunci ini, yang paling sering digunakan adalah `italic` (cetak miring) dan `normal`.

``` css
.special {
  font-style: italic;
}
```

### Properti `font-variant`

Terkadang kita ingin tulisan kita dicetak dalam kapital kecil. Untuk kasus seperti ini kita gunakan properti `font-variant`. Properti `font-variant` menerima tiga nilai: `normal`, `small-caps`, dan `inherit`. Yang paling sering digunakan adalah `normal` dan `small-caps` yang akan mengubah font menjadi cetak normal atau kapital kecil.

```
.firm {
  font-variant: small-caps;
}
```

### Properti `font-weight`

Terkadang kita ingin membuat tulisan kita menjadi cetak tebal, atau ingin menentukan secara spesifik berat dari typeface. Untuk kasus ini maka kita gunakan properti `font-weight`. Properti `font-weight` menerima kata kunci atau nilai numerik.

Kata kuncinya yaitu `normal`, `bold`, `bolder`, `lighter`, dan `inherit`. Dari semua nilai ini, disarankan untuk menggunakan `normal` dan `bold` untuk mengubah tulisan menjadi cetak normal atau cetak tebal. Dari pada menggunakan `bolder` atau `lighter`, lebih menggunakan nilai numerik untuk lebih spesifik.

``` css
.daring {
  font-weight: bold;
}
```

Nilai numerik 100, 200, 300, 400, 500, 600, 700, 800, dan 900 merupakan nilai spesifik dari bobot typeface. Nilai 100 menyatakan bobot tertipis, dan 900 menyatakan bobot tertebal. Kata kunci `normal` dipetakan ke 400, dan `bold` ke 700. Nilai yang kurang dari 400 akan lebih tipis dan nilai yang lebih dari 700 akan lebih tebal.

``` css
.daring {
  font-weight: 600;
}
```

<hr>

###### Bobot Typeface

Sebelum menggunakan nilai numerik, kita harus memeriksa apakah typeface yang kita gunakan mendukung bobot yang kita inginkan. Dengan mencoba bobot yang tidak tersedia dari typeface kita maka akan dipilih bobot yang tersedia yang paling dekat.

Sebagai contoh, typeface Times New Roman memiliki dua bobot: `normal` atau 400 dan `bold` atau 700. Berusaha untuk menggunakan bobot 900 akan membuat typeface menggunakan bobot 700.

<hr>

### Properti `line-height`

Jarak antar baris didefinisikan oleh properti `line-height`. Properti `line-height` menerima semua nilai panjang.

Latihan terbaik untuk keterbacaan untuk menetapkan nilai properti `font-size` menjadi satu setengah kali. Hal ini dapat dilakukan dengan menetapkan nilai `line-height` menjadi `150%` atau hanya `1.5`. Tetapi jika kita bekerja dengan grid, sebaiknya gunakan nilai pixel.

``` css
body {
  line-height: 22px;
}
```

Properti `line-height` juga dapat digunakan untuk meratatengahkan secara vertikal tulisan satu baris yang terdapat di dalam elemen. Dengan menggunakan nilai yang sama untuk properti `line-height` dan `height` akan meratatengahkan tulisan:

``` css
.btn {
  height: 22px;
  line-height: 22px;
}
```

Teknik ini dapat digunakan untuk tombol, pesan peringatan, atau blok tulisan satu baris.

### Properti Font Versi Pendek

Semua properti yang disebutkan sebelumnya dapat digabungkan menjadi satu properti versi pendek. Properti `font` dapat menerima banyak nilai properti berbasis `font`. Urutannya yaitu: `font-style`, `font-variant`, `font-weight`, `font-size`, `line-height`, dan `font-family`.

Sebagai versi pendek, semua nilai ini ditulis tanpa koma (kecuali nama font yang digunakan oleh properti `font-family`). Tanda garis miring `/` digunakan untuk memisahkan antara nilai properti `font-size` dan `line-height`.

Dalam menggunakan nilai versi pendek, semua properti merupakan opsional kecuali nilai dari properti `font-size` dan `font-family`.

``` css
html {
  font: italic small-caps bold 14px/22px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
```

### Semua Properti Font Bersama-sama

Berikut contoh yang menggunakan semua properti berbasis `font`. 

**HTML**

``` html
<h2><a href="#">I Am a Builder</a></h2>

<p class="byline">Posted by Shay Howe</p>

<p>Every day I see designers and developers working alongside one another. They work intelligently in pursuit of business objectives. They work diligently making exceptional products. They solve real problems and take pride in their work. They are builders. <a href="#">Continue&#8230;</a></p>
```

**CSS**

``` css
h2,
p {
  color: #555;
  font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
a {
  color: #0087cc;
}
a:hover {
  color: #ff7b29;
}
h2 {
  font-size: 22px;
  font-weight: bold;
  margin-bottom: 6px;
}
.byline {
  color: #9799a7;
  font-family: Georgia, Times, "Times New Roman", serif;
  font-style: italic;
  margin-bottom: 18px;
}
```

<hr>

###### Pseudo-Class CSS

Pseudo-class adalah kata kunci yang dapat ditambahkan pada akhir selektor untuk memberi style pada elemen ketika suatu state terjadi.

Contohnya yaitu pseudo-class `:hover` yang digunakan untuk memberi style ketika mouse user berada diatas elemen tersebut. Ketika digunakan dengan elemen `<a>`, semua elemen `<a>` akan menerima style unik ketika mouse berada pada elemen tersebut.

<hr>

## Menerapkan Properti Text <a name="3"></a>

Kita dapat menentukan bagaimana meratakan tulisan, mendekorasi, mengindentasi, menransformasi, dan membuat jarak antar kata.

### Properti `text-align`

Meratakan tulisan merupakan bagian penting dalam membuat halaman web, yang bisa dilakukan dengan menggunakan properti `text-align`. Properti `text-align` mempunyai lima nilai: `left`, `right`, `center`, `justify`, dan `inherit`. Nilai-nilai ini membuat tulisan menjadi rata kiri, rata kanan, rata tengah dan rata kiri kanan.

``` css
p {
  text-align: center;
}
```

### Properti `text-decoration`

Properti `text-decoration` digunakan untuk mendekorasi tulisan. Properti ini menerima kata kunci `none`, `underline`, `overline`, `line-through`, dan `inherit`. Yang paling sering digunakan adalah `underline`, yang dipakai untuk default style untuk link.

``` css
.note {
  text-decoration: underline;
}
```

Properti `text-decoration` dapat menerima nilai lebih dari satu, yang dipisahkan dengan spasi.

### Properti `text-indent`

Properti `text-indent` dapat digunakan untuk memberikan indentasi pada baris pertama dari tulisan. Properti ini dapat meneriman semua nilai panjang termasuk pixel, titik, persentase, dan lain-lain. Nilai positif akan memberikan indentasi ke dalam, sedangkan negatif akan memberikan indentasi ke luar.

``` css
p {
  text-indent: 20px;
}
```

### Properti `text-shadow`

Properti `text-shadow` dapat membuat kita memilih untuk menambahkan bayangan atau banyak bayangan pada tulisan kita. Properti ini menerima  empat nilai, tiga nilai pertama merupakan panjang dan nilai terakhir merupakan warna.

Pada tiga nilai panjang, nilai pertama menggeser bayangan secara horizontal, nilai kedua menggeser bayangan secara vertikal, dan yang ketiga adalaha jari-jari keburaman dari bayangan. Nilai yang terkahir yaitu nilai warna, dapat menerima nilai warna apapun.

``` css
p {
  text-shadow: 3px 6px 2px rgba(0, 0, 0, .3);
}
```

Dengan menggunakan nilai panjang negatif, akan menggeser bayangan ke kiri atau ke atas.

Bayangan pada tulisan dapat dibuat lebih dari satu, dengan memisahkannya dengan koma.

<hr>

###### Properti `box-shadow`

Jika kita ingin memberikan bayangan pada elemen kita dan bukan hanya tulisannya saja maka kita menggunakan properti `box-shadow`.

Properti `box-shadow` bekerja sama seperti properti `text-shadow` menerima nilai panjang dan warna.

Properti `box-shadow` memiliki nilai keempat tambahan sebelum nilai warna, yaitu penyebaran bayangan. Untuk nilai positif, bayangan akan menyebar melebihi ukuran elemennya, sedangkan untuk negatif bayangan akan menyusut kurang dari ukuran elemennya.

Terakhir, properti `box-shadow` memuat nilai opsional `inset` pada awal peletakan nilai, untuk menentukan apakah bayangan akan diletakan di luar elemen atau di dalam elemen.

<hr>

### Properti `text-transform`

Properti `text-transform` akan mengubah tulisan tanpa perlu alternatif typeface. Properti `text-transform` menerima lima input: `none`, `capitalize`, `uppercase`, `lowercase`, dan `inherit`.

Nilai `capitalize` akan membuat huruf pertama dari setiap kata menjadi kapital. Nilai `uppercase` akan membuat semua huruf menjadi kapital, sedangkan `lowercase` akan membuat semua huruf menjadi huruf kecil. Nilai `none` akan menghilangkan semua nilai turunan ini.

``` css
p {
  text-transform: uppercase;
}
```

### Properti `letter-spacing`

Dengan menggunakan properti `letter-spacing`, kita dapat menentukan lebar spasi antar tiap huruf. Nilai positif akan membuat jaraknya menjadi lebih lebar sedangkan negatif akan membuat jaraknya menjadi sempit. Nilai `none` akan mengembalikan jaraknya ke semula.

Dengan menggunakan nilai relatif pada properti `letter-spacing`, akan meyakinkan bahwa jarak antar huruf akan tetap walau ukuran tulisannya diubah.

``` css
p {
  letter-spacing: -.5em;
}
```

### Properti `word-spacing`

Sama seperti properti `letter-spacing`, kita dapat menentukan lebar spasi antar kata dengan menggunakan properti `word-spacing`. Properti `word-spacing` menerima semua nilai panjang dan kata kunci sama seperti properti `letter-spacing`.

``` css
p {
  word-spacing: .25em;
}
```
### Semua Properti Teks Bersama-sama

Kita tambahkan properti berbasis text pada contoh sebelumnya.

**HTML**

``` html
<h2><a href="#">I Am a Builder</a></h2>

<p class="byline">Posted by Shay Howe</p>

<p class="intro">Every day I see designers and developers working alongside one another. They work intelligently in pursuit of business objectives. They work diligently making exceptional products. They solve real problems and take pride in their work. They are builders. <a href="#">Continue&#8230;</a></p>
```

**CSS**

``` css
h2,
p {
  color: #555;
  font: 13px/20px "Helvetica Neue", Helvetica, Arial, sans-serif;
}
a {
  color: #0087cc;
}
a:hover {
  color: #ff7b29;
}
h2 {
  font-size: 22px;
  font-weight: bold;
  letter-spacing: -.02em;
  margin-bottom: 6px;
}
h2 a {
  text-decoration: none;
  text-shadow: 2px 2px 1px rgba(0, 0, 0, .2);
}
.byline {
  color: #9799a7;
  font-family: Georgia, Times, "Times New Roman", serif;
  font-style: italic;
  margin-bottom: 18px;
}
.intro {
  text-indent: 15px;
}
.intro a {
  font-size: 11px;
  font-weight: bold;
  text-decoration: underline;
  text-transform: uppercase;
}
```

## Menggunakan Web-safe Font <a name="4"></a>

Secara default, ada beberapa font yang sudah diinstall pada komputer, tablet, smartphone atau perangkat yang dapat browsing web. Dengan adanya font ini, maka kita dapat gunakan font-nya dengan bebas tanpa memperdulikan pada perangkat apa web kita dilihat. Font ini bernama "Web-safe font." Font-font ini hanya ada beberapa dan berikut list font yang paling aman:
* Arial
* Courier New, Courier
* Garamond
* Georgia
* Lucida Sans, Lucida Grande, Lucida
* Palatino Linotype
* Tahoma
* Times New Roman, Times
* Trebuchet
* Verdana

### Menyisipkan Font Web

Kita juga dapat mengunggah font kita ke server dan menggunakannya dengan menggunakan CSS at-rule `@font-face`. Menyisipkan font web seperti berikut: Pertama, kita gunakan CSS at-rule `@font-face` untuk mengidentifikasi nama font dengan menggunakan properti `font-family` dan juga sumber dari font kita dengan menggunakan properti `src`. Dari sini kita dapat menggunakan font-nya dengan mengikutsertakan namanya pada nilai properi `font-family`.

``` css
@font-face {
  font-family: "Lobster";
  src: local("Lobster"), url("lobster.woff") format("woff");
}
body {
  font-family: "Lobster", "Comic Sans", cursive;
}
```

Setiap typeface yang kita gunakan belum tentu legal karena typeface merupakan hasil karya seni dan terdapat lisensi untuk font tersebut.

Perusahaan seperti Typekit dan Fontdeck memuat font yang berlisensi, sedangkan Google Fonts memuat font dengan lisensi gratis. Sebelum mengunggah font kita, pastikan kita mempunyai izin untuk melakukannya.

## Memuat Rujukan &amp; Kuotasi <a name="5"></a>

Menulis online terkadang memerlukan rujukan ke sumber lain atau kuotasi. Rujukan dan kuotasi dapat dibuat secara semanti pada HTML dengan menggunakan elemen `<cite>`, `<q>`, dan `<blockqoute>`.

Secara umum, gunakan aturan berikut untuk menggunakan elemen-elemen ini:
* `<cite>`: Digunakan untuk merujuk kerja kreatif, pengarang, dan sumber
* `<q>`: Digunakan untuk kuotasi pendek
* `<blockquote>`: Digunakan untuk kuotasi yang lebih panjang

### Merujuk Karya Kreatif

Elemen inline `<cite>` digunakan pada HTML untuk spesifik merujuk karya kreatif, elemennya harus memuat judul karyanya, nama pengarang, atau referensi URL ke hasil karya. Secara default, konten yang dibungkus dalam elemen `<cite>` akan dicetak miring.

Sebagai tambahan, sebaiknya tambahkan hyperlink ke sumber asal untuk rujukannya.

``` html
<p>The book <cite><a href="http://www.amazon.com/Steve-Jobs-Walter-Isaacson/dp/1451648537">Steve Jobs</a></cite> is truly inspirational.</p>
```

### Kuotasi Dialog &amp; Prosa

Sering dialog atau prosa dikuotasi dalam baris tulisan kita. Untuk tujuan ini, elemen inline `<q>` dapat digunakan. Elemen `<q>` secara semantik digunakan untuk kuotasi dialog atau prosa dan tidak untuk tujuan lainnya.

Secara default, browser akan menambahkan tanda quotasi dan akan berubah tergantung bahasa yang kita gunakan pada atribut global `lang`.

``` html
<p>Steve Jobs once said, <q>One home run is much better than two doubles.</q></p>
```

### Rujukan Dialog &amp; Prosa

Atribut tambahan yang dapat ditambahkan pada elemen `<q>` adalah `cite`. Atribut `cite` akan bekerja sebagai referensi rujukan ke kuotasi dalam bentuk URL. Atribut ini tidak mengubah penampilan elemen, ini hanya menambah nilai pada screen reader dan perangkat yang lain. Karena atribut ini tidak dapat dilihat pada browser, maka sebaiknya tambahkan hyperlink ke sumber dari kuotasi yang asli.

``` html
<p><a href="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">Steve Jobs</a> once said, <q cite="http://www.businessweek.com/magazine/content/06_06/b3970001.htm">One home run is much better than two doubles.</q></p>
```

### Kuotasi Luar

Untuk memuat kuotasi yang besar dan memerlukan beberapa baris maka kita memerlukan elemen `<blockquote>`. Elemen `<blockquote>` merupakan elemen level blok yang dapat memuat elemen level blok lainnya, termasuk heading dan paragraf.

``` html
<blockquote>
  <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
</blockquote>
```

### Rujukan Luar

Kuotasi yang panjang di dalam elemen `<blockquote>` sering memuat rujukan. Rujukan ini dapat menggunakan atribut `cite` dan elemen `<cite>`.

Atribut `cite` dapat digunakan pada elemen `<blockquote>` sama seperti elemen `<q>` untuk memuat rujukan dalam bentuk URL. Elemen `<cite>` dapat ditaruh di akhir kuot untuk menunjukan sumber asal dari kuot tersebut.

``` html
<blockquote cite="http://money.cnn.com/magazines/fortune/fortune_archive/2000/01/24/272277/index.htm">
  <p>&#8220;In most people&#8217;s vocabularies, design is a veneer. It&#8217;s interior decorating. It&#8217;s the fabric of the curtains, of the sofa. But to me, nothing could be further from the meaning of design. Design is the fundamental soul of a human-made creation that ends up expressing itself in successive outer layers of the product.&#8221;</p>
  <p><cite>&#8212; Steve Jobs in <a href="http://money.cnn.com/ magazines/fortune/fortune_archive/2000/01/24/272277/index.htm"> Fortune Magazine</a></cite></p>
</blockquote>
```

## Rangkuman

Hal yang sudah dipelajari:
* Menambahkan warna pada tulisan
* Menerapkan properti berbasis `font`, seperti `font-family`, `font-size`, `font-style`, `font-weight`, dll.
* Menerapkan properti berbasis `text`, seperti `text-align`, `text-decoration`, `text-indent`, `text-shadow`, dll.
* Sejarah web-safe font dan cara menysipkan web font kita
* Bagaimana cara untuk membuat rujukan dan kuotasi
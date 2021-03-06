<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Mengenal HTML

---

<!-- page_number: true -->
<!-- *template: invert -->
## Semantik

---

Semantik adalah memberikan arti dan struktur dari elemen yang tepat untuk konten pada halaman kita.

Keuntungannya:
* dapat dibaca oleh screen readers
* meningkatkan ranking pada search engines
* mudah untuk diatur karena struktur konten yang lebih jelas

---

###### Elemen Blok vs. Inline

Elemen level-blok dimulai dari baris baru. Elemen ini akan mengambil tempat selebar jendela browser. Elemen lainnya akan berada diatas dan dibawahnya tetapi tidak dapat disamping kanan kirinya. Elemen level blok dapat berada di dalam elemen level blok lainnya. Elemen level inline juga dapat berada di dalam elemen level blok. Contohnya yaitu `<h1>`, ... , `<h6>`, `<p>`, `<div>`, dll.

Elemen level inline tidak dimulai pada baris baru. Mereka mengikuti alur dokumen. Lebarnya hanya selebar isi kontennya. Elemen level blok tidak dapat berada di dalam elemen level inline. Contohnya yaitu `<b>`, `<i>`, `<img>`, `<a>`, `<span>` dll.

---

<!-- page_number: true -->
<!-- *template: invert -->
## Divisions &amp; Spans

---

Tidak semua elemen HTML memiliki makna semantik, contohnya yaitu elemen `<div>` dan `<span>`. Kedua ini hanya sebuah container yang digunakan untuk keperluan style.

Beri nilai `id` dan `class` yang sesuai dengan konten dari elemennya, khususnya untuk elemen `<div>` dan `<span>`.

**Contoh**:

``` html
<!-- Division -->
<div class="social">
  <p>I may be found on...</p>
  <p>Additionally, I have a profile on...</p>
</div>

<!-- Span -->
<p>Soon we'll be <span class="tooltip">writing HTML</span> with the best of them.</p>
```

---

###### Komentar

Tanda `<!-- isi komentar -->` menyatakan komentar pada HTML. Komentar ini tidak akan ditampilkan pada browser dan hanya untuk kebutuhan dokumentasi. Komentar untuk CSS yaitu `/* isi komentar */`.

---

<!-- page_number: true -->
<!-- *template: invert -->
## Elemen Berbasis Teks

---

### Heading

Heading merupakan elemen blok-level, yang terdiri dari 6 tingkatan, yaitu dari `<h1>` sampai `<h6>`.
Heading membantu membagi konten halaman dan menjadi penanda pada halaman.
Mereka juga membantu search engine untuk meng-index dan mengenali konten halaman.
Level heading harus digunakan dimana terdapat nilai semantiknya, dan tidak digunakan untuk membuat teks menjadi bold atau besar.

---

**Contoh:**
``` html
<h1>Heading Level 1</h1>
<h2>Heading Level 2</h2>
<h3>Heading Level 3</h3>
<h4>Heading Level 4</h4>
<h5>Heading Level 5</h5>
<h6>Heading Level 6</h6>
```

---

### Paragraf

Heading biasanya didukung oleh paragraf, yang didefinisikan oleh elemen level blok `<p>`.
Paragraf berisi informasi yang dibutuhkan dari halaman web kita.

**Contoh:**
``` html
<p>Steve Jobs was a co-founder and longtime chief executive officer at Apple. On June 12, 2005, Steve gave the commencement address at Stanford University.</p>

<p>In his address Steve urged graduates to follow their dreams and, despite any setbacks, to never give up&ndash;advice which he sincerely took to heart.</p>

```

---

### Teks Cetak Tebal dengan Menggunakan Strong

Gunakan elemen level inline `<strong>` untuk membuat teks menjadi catak tebal dan menunjukkan teks tersebut penting.
Ada dua elemen yang membuat teks menjadi catak tebal, yaitu: elemen `<strong>` dan `<b>`.
Perbedaanya yaitu: elemen `<strong>` digunakan untuk teks yang bersifat penting. Sedangkan elemen `<b>` hanya digunakan pada teks yang perlu style catak tebal.

---

**Contoh:**
``` html
<!-- Strong importance -->
<p><strong>Caution:</strong> Falling rocks.</p>

<!-- Stylistically offset -->
<p>This recipe calls for <b>bacon</b> and <b>baconnaise</b>.</p>
```

---

### Teks Cetak Miring dengan Menggunakan Emphasis

Untuk membuat tulisan bercetak miring, dengan memberikan emphasis pada tulisan tersebut, maka kita gunakan elemen level-inline `<em>`.
Sama sepeti bold, terdapat dua elemen yang dapat membuat tulisan menjadi bercetak miring, yaitu: elemen `<em>` dan `<i>`.
Perbedaannya yaitu: elemen `<em>` memberi tekanan emphasis pada tulisan, sedangkan elemen `<i>` untuk membuat tulisan seolah-olah bernada lain.

---

**Contoh:**
``` html
<!-- Stressed emphasis -->
<p>I <em>love</em> Chicago!</p>

<!-- Alternative voice or tone -->
<p>The name <i>Shay</i> means a gift.</p>
```

---

HTML5 memperkenalkan elemen struktur, yaitu: elemen `<header>`, `<nav>`, `<article>`,  `<section>`, `<aside>`, dan `<footer>`.
Semuanya merupakan elemen level blok yang digunakan untuk tujuan struktur semantik.

---

<!-- page_number: true -->
<!-- *template: invert -->
## Membangun Struktur

---

### Header

Header elemen digunakan untuk mengelompokan bagian atas dari halaman, artikel, section atau bagian lain dari halaman.
Umumnya, elemen `<header>` memuat heading, tulisan pembuka dan juga navigasi.

``` html
<header>...</header>
```

---

### Navigasi

Elemen `<nav>` untuk mengelompokan link navigasi utama pada halaman.
Umumnya link yang terdapat didalam elemen `<nav>` akan terhubung dengan halaman lain pada website yang sama atau ke bagian lain pada halaman yang sama.

``` html
<nav>...</nav>
```

---

### Artikel

Elemen `<article>` digunakan untuk membuat bagian yang bebas dan tidak tergantung pada konten yang lain sehingga dapat digunakan kembali.
Umumnya elemen `<article>` digunakan untuk menandai postingan blog, artikel koran, konten yang dikumpulkan oleh pengguna, dan lainnya.
Jika konten yang terdapat dalam elemen `<article>` dipindahkan ke email atau diprint, maka kontennya harus tetap masuk akal.

``` html
<article>...</article>
```

---

### Section

Elemen `<sction>` digunakan untuk menglompokan konten yang bertema sama, dan biasanya, tapi tidak selalu, memuat heading.
Elemen `<section>` umumnya digunakan untuk membuat hierarki pada halaman.

``` html
<section>...</section>
```

---

### Aside

Elemen `<aside>` memuat konten seperti sidebars, inserts, atau penjelasan singkat, yang masih berhubungan dengan konten di sekitarnya.
Contohnya yaitu dalam menggunakan elemen `<article>`, elemen `<aside>` dapat digunakan untuk mengidentifikasi konten yang berhubungan dengan penulis dari artikel tersebut.

``` html
<aside>...</aside>
```

---

### Footer

Elemen `<footer>` mengidentifikasikan penutup atau akhir dari halaman.
Umumnya elemen `<footer>` berada pada bagian bawah dari parent.
Konten dari elemen `<footer>` harus informasi yang berhubungan dan tidak menyimpang dari dokumen atau bagian dimana dia berada.

``` html
<footer>...</footer>
```

---

<!-- page_number: true -->
<!-- *template: invert -->
## Membuat Hyperlinks

---

Sejajar dengan teks, salah satu unsur penting dari internet adalah hyperlink, dapat membuat tautan dari satu halaman ke halaman lainnya. Hyperlink dapat dibuat dengan menggunakan elemen level inline `<a>`. Untuk membuat tautan dari satu halaman ke halaman yang lain, kita gunakan atribut `href`, dikenal sebagai hyperlink reference. Nilai dari atribut `href` merupakan alamat tujuan dari link-nya.

---

**Contoh**:

``` html
<a href="http://makersinstitute.id">Makers Institute</a>
```

> Pada dasrnya, elemen level inline tidak dapat memuat elemen level blok. Tetapi pada HTML5, elemen level inline `<a>` diperbolehkan untuk memuat elemen level blok.

---

### Path Relatif dan Absolut

Nilai dari atribut `href` merupakan sebuah path. Ada 2 jenis path, yaitu:
* Path realtif: tidak menyertakan domain (.com, .org, .edu, dll). Atribut hanya memuat nama file yang akan dituju (contoh: `about.html`). Jika file `about.html` berada di dalam folder `pages`, maka path relatifnya yaitu `pages/about.html`.
* Terhubung dengan website di luar website kita memerlukan path absolut, dengan atribut `href` memerlukan nama domain secara utuh. Tautan ke google membutuhkan `href` yang bernilai `http://google.com`, dimulai dengan `http` dan diakhiri dengan `.com`.

---

**Contoh**:
``` html
<!-- Relative Path -->
<a href="about.html">About</a>

<!-- Absolute Path -->
<a href="http://www.google.com/">Google</a>
```

---

### Membuat Tautan ke Alamat Email

Untuk membuat link email, nilai dari atribut `href` harus dimulai dengan `mailto:` diikuti dengan alamat email yang dituju. Contoh: `mailto:daniel@makersinstitute.com`. Untuk menambahkan subject maka kita tambahkan parameter `subject=` setelah alamat email. Parameter pertama setelah alamat email harus diikuti oleh tanda tanya `?`. Kata-kata pada subjek harus dipisah oleh spasi yang dienkode menjadi `%20`. Untuk menambahkan teks pada bagian body kita gunakan parameter `body=`. Untuk memisahkan antara parameter pertama dan kedua kita gunakan tanda ampersand `&`. Untuk pindah baris kita gunakan enkode `%0A`. **Contoh**:

``` html
<a href="mailto:daniel@makersinstitute.com?subject=Reaching%20Out&body=How%20are%20you">Email Me</a>
```

---

### Membuka Tautan pada Jendela Baru

Pada dasarnya link dibuka pada jendela yang sama saat mereka diklik, tetapi link juga dapat dibuka pada jendela baru.
Untuk melakukannya tambahkan atribut `target` dengan nilai `_blank`. 

**Contoh**:
``` html
<a href="http://makersinstitute.id/" target="_blank">Makers Institute</a>
```

---

### Membuat Tautan ke Suatu Bagian dari Halaman yang Sama

Kita dapat membuat link yang bertaut pada halaman yang sama dengan menetapkan atribut `id` pada elemen yang ingin kita tuju, dan gunakan nilai dari `id` tersebut pada atribut `href` kita.

**Contoh**:
``` html
<body id="top">
  ...
  <a href="#top">Back to top</a>
  ...
</body>
```

---

## Rangkuman

Hal yang sudah dipelajari:
* Apa itu semantik dan kenapa semantik itu penting
* `<div>` dan `<span>` dan perbedaan antara elemen level blok dan level inline.
* Pemilihan elemen berbasis teks yang tepat untuk konten halaman kita.
* Struktur elemen HTML5 dan bagaimana mengatur struktur konten dan halaman kita.
* Bagaimana cara menggunakan hyperlink untuk berpindah antar halaman web atau situs web.
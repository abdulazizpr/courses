<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Mengatur Latar Belakang &amp; Gradien

**Outline:**
* [List Tak Berurutan](#1)
* [List Berurutan](#2)
* [List Deskripsi](#3)
* [List Bersarang](#4)
* [Memberikan Style pada Item List](#5)
* [Menampilkan secara Horizontal](#6)

HTML memiliki tiga list yang berbeda: tak berurutan, berurutan, dan deskripsi. Untuk memilih jenis list yang digunakan tergantung konten dan juga makna sematiknya.

<a name="1"></a>
## List Tak Berurutan

Untuk membuat list tak berurutan pada HTML menggunakan elemen level blok `<ul>` dengan setiap item-nya menggunakan elemen `<li>`.

Secara default, sebagian browser akan menambahkan `margin` vertikal dan `padding` kiri ke elemen `<ul>` dan menambahkan titik solid ke elemen `<li>`. Titik solid ini dapat diganti menggunakan CSS.

``` html
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```
<a name="2"></a>
## List Berurutan

List berurutan mirip dengan list tak berurutan, yang membedakan yaitu list berurutan ditandai oleh angka, bukan titik solid.

``` html
<ol>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>
```

List berurutan mempunyai atribut khusus, yaitu `start` dan `reversed`.

### Atribut `start`

Atribut `start` menentukan pada angka berapa list dimulai. Secara default list-nya akan dimulai dari 1. Atribut `start` hanya menerima nilai bilangan bulat, walaupun list-nya dapat diurutkan dengan sistem yang lain, misalnya bilangan romawi.

``` html
<ol start="30">
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>
```

### Atribut `reversed`

Atribut `reversed` akan memutarbalikkan urutan list. Misalkan listnya dari 1 sampai 5, maka yang ditampilkan adalah urutan sebaliknya yaitu dari 5 ke 1.

Atribut `reversed` merupakaan atribut boolean, dan tidak menerima nilai apapun.

``` html
<ol reversed>
  <li>Head north on N Halsted St</li>
  <li>Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>
```

### Atribut `value`

Atribut `value` dapat digunakan untuk individual elemen `<li>` untuk mengubah nomor item tersebut. Item setelahnya akan mengikuti nomor tersebut.

``` html
<ol>
  <li>Head north on N Halsted St</li>
  <li value="9">Turn right on W Diversey Pkwy</li>
  <li>Turn left on N Orchard St</li>
</ol>
```

<a name="3"></a>
## List Deskripsi

List deskripsi digunakan untuk list istilah-istilah yang disertai dengan deskripsinya.

Untuk membuat list deskripsi menggunakan elemen `<dl>`. Untuk membuat itemnya menggunakan elemen `<dt>` dan deskripsinya menggunakan `<dd>`.

Elemen `<dd>` harus setelah elemen `<dt>`.

``` html
<dl>
  <dt>study</dt>
  <dd>The devotion of time and attention to acquiring knowledge on an academic subject, especially by means of books</dd>
  <dt>design</dt>
  <dd>A plan or drawing produced to show the look and function or workings of a building, garment, or other object before it is built or made</dd>
  <dd>Purpose, planning, or intention that exists or is thought to exist behind an action, fact, or material object</dd>
  <dt>business</dt>
  <dt>work</dt>
  <dd>A person's regular occupation, profession, or trade</dd>
</dl>
```

<a name="4"></a>
## List Bersarang

List dapat bersarang, yaitu list dapat diletakkan didalam list yang lain. Meletakkan list yang lain harus didalam elemen `<li>`.

``` html
<ol>
  <li>Walk the dog</li>
  <li>Fold laundry</li>
  <li>
    Go to the grocery and buy:
    <ul>
      <li>Milk</li>
      <li>Bread</li>
      <li>Cheese</li>
    </ul>
  </li>
  <li>Mow the lawn</li>
  <li>Make dinner</li>
</ol>
```

Penanda item akan berubah untuk seberapa dalam list tersebut bersarang. Tapi kita dapat mengatur hal tersebut dengan menggunakan CSS.

<a name="`5"></a>
## Memberikan Style pada Item List

Style default untuk list tak berurutan adalah titik solid sedangkan untuk list berurutan adalah angka.

### Properti `list-style-type`

Properti `list-style-type` digunakan untuk mengubah penanda item list. Nilai yang tersedia dari persegi, bilangan desimal, sampai penomoran Armenian. Style-nya dapat diletakan pada elemen `<ul>`, `<ol>` atau `<li>`. Dengan ini memungkinkan untuk memberikan list nomor pada list tak berurutan, dan penanda nonnumerik pada list berurutan.

**HTML**

``` html
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```

**CSS**

``` css
ul {
  list-style-type: square;
}
```
### Nilai dari Properti `list-style-type`

Berikut list dari nilai dari properti `list-style-type`:

**Nilai:** `none`
**Konten:** Tidak ada penanda

**Nilai:** `disc`
**Konten:** Lingkaran berisi

**Nilai:** `circle`
**Konten:** Lingkaran kosong

**Nilai:** `square`
**Konten:** Persegi berisi

**Nilai:** `decimal`
**Konten:** Bilangan desimal

**Nilai:** `decimal-leading-zero`
**Konten:** Bilangan desimal yang dimulai dengan nol didepannya

**Nilai:** `lower-roman`
**Konten:** Huruf kecil bilangan romawi

**Nilai:** `upper-roman`
**Konten:** Huruf kapital bilangan romawi

**Nilai:** `lower-greek`
**Konten:** Huruf kecil Yunani klasik

**Nilai:** `lower-alpha` / `lower-latin`
**Konten:** Huruf kecil huruf ASCII

**Nilai:** `upper-alpha` / `upper-latin`
**Konten:** Huruf kapital huruf ASCII

**Nilai:** `armenian`
**Konten:** Penomoran tradisional Armenian

**Nilai:** `georgian`
**Konten:** Penomoran tradisional Georgian

### Menggunakan Gambar sebagai Penanda Item List

Terkadang kita nilai default dari properti `list-style-type` tidak cukup. Kita dapat menambahkan gambar latar belakang pada elemen `<li>`.

Prosesnya yaitu membuang style default penanda item dengan menggunakan nilai `none` pada properti `list-style-type` dan menambahkan gambar latar dan memberikan padding pada elemen `<li>`.

**HTML**

``` html
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```

**CSS**

``` css
li {
  background: url("arrow.png") 0 50% no-repeat;
  list-style-type: none;
  padding-left: 12px;
}
```

### Properti `list-style-position`

Secara defult penanda item list akan berada di sebalah kiri konten elemen `<li>`. Dengan menggunakan properti `list-style-position` kita dapat mengubah nilai defaultnya menjadi `outside`, `inside`, atau `inherit`.

Nilai `outside` digunakan untuk menempatkan penanda list disebelah kiri elemen `<li>` dan konten tidak dapat membungkus dibawahnya. Nilai `inside` digunakan untuk membuat konten dapat membungkus penanda item pada baris selanjutnya.

**HTML**

``` html
<ul>
  <li>Cupcakes...</li>
  <li>Sprinkles...</li>
</ul>
```

**CSS**

```css
ul {
  list-style-position: inside;
}
```

### Properti `list-style` Versi Pendek

Properti `list-style-type` dan `list-style-position` dapat digabungkan menjadi properti `list-style`. Urutan dari versi pendek ini adalah `list-style-type` kemudian `list-style-position`.

``` css
ul {
  list-style: circle inside;
}
ol {
  list-style: lower-roman;
}
```
<a name="6"></a>
## Menampilkan secara Horizontal

Terkadang kita ingin menampilkan list secara mendatar. Hal ini dapat dilakukan dengan mengubah properti `display` elemen `<li>` menjadi `inline` atau `inline-block` atau memberikan float.

### Menampilkan list

Cara paling cepat yaitu mengubah properti `display` elemen `<li>` menjadi `inline-block`. Dengan `inline-block` kita dapat mengatur `margin` vertikal.

Ketika mengubah nilai properti `display` menjadi `inline` atau `inline-block` maka penanda item akan hilang.

**HTML**

``` html
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```

**CSS**

```css
li {
  display: inline-block;
  margin: 0 10px;
}
```

### List dengan Float

Mengubah properti `display` menjadi `inline` atau `inline-block` memang cepat, tetapi menghilangkan penanda item. 

Memberikan nilai `left` pada properti `float` dari elemen `<li>` akan membuat semua elemen `<li>` akan berada disamping satu dengan yang lain. Secara default penanda item akan berada di atas elemen `<li>` selanjutnya. Untuk mengatasi hal tersebut kita tambahkan `margin` dan `padding`.

**HTML**

``` html
<ul>
  <li>Orange</li>
  <li>Green</li>
  <li>Blue</li>
</ul>
```

**CSS**

```css
li {
  float: left;
  margin: 0 20px;
}
```

Ingat kita harus menggunakan teknik clearfix untuk memperbaiki flow dokumen.

### Contoh List Navigasi

Berikut contoh menu navigasi yang menggunakan list tak berurutan dengan elemen `<li>` ditampilkan sebagai elemen `inline-block`.

**HTML**

``` html
<nav class="navigation">
  <ul>
    <li><a href="#">Profile</a></li><!--
    --><li><a href="#">Settings</a></li><!--
    --><li><a href="#">Notifications</a></li><!--
    --><li><a href="#">Logout</a></li>
  </ul>
</nav>
```

**CSS**

```css
.navigation ul {
  font: bold 11px "Helvetica Neue", Helvetica, Arial, sans-serif;
  margin: 0;
  padding: 0;
  text-transform: uppercase;
}
.navigation li {
  display: inline-block;
}
.navigation a {
  background: #395870;
  background: linear-gradient(#49708f, #293f50);
  border-right: 1px solid rgba(0, 0, 0, .3);
  color: #fff;
  padding: 12px 20px;
  text-decoration: none;
}
.navigation a:hover {
  background: #314b60;
  box-shadow: inset 0 0 10px 1px rgba(0, 0, 0, .3);
}
.navigation li:first-child a {
  border-radius: 4px 0 0 4px;
}
.navigation li:last-child a {
  border-right: 0;
  border-radius: 0 4px 4px 0;
}
```

## Rangkuman

Hal yang sudah dipelajari:
* Bagaimana cara membuat list tak berurutan, list berurutan, dan list deskripsi
* Bagaimana membuat list yang bersarang di dalam list lainnya
* Bagaimana cara mengubah style dan posisi dari penanda item list
* Bagaimana cara menggunakan gambar latar belakang sebagai penanda item list
* Bagaimana menampilkan list secara horizontal dengan menggunakan display dan float
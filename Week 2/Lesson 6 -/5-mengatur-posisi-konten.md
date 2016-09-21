<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Mengatur Posisi Konten

**Outline:**
* Mengatur Posisi dengan Float
* Mengatur Posisi dengan Inline-Blok
* Membuat Layout yang Dapat Dipakai Ulang
* Menempatkan Elemen Secara Unik

## Mengatur Posisi dengan Float

Salah satu cara untuk menempatkan elemen pada halaman yaitu menggunakan properti `float`. Intinya, dengan properti `float` kita dapat memilih elemen, mengeluarkannya dari flow halaman, dan menempatkannya pada sisi kiri atau kanan dari elemen parent-nya. Semua elemen lain akan mengalir mengisi sekitar elemen tersebut. Elemen `<img>` yang float ke sisi paragraf teks akan dikelilingi atau dibungkus oleh teks tersebut.

Ketika properti `float` digunakan pada beberapa elemen pada saat yang bersamaan, maka kita dapat membuat layout dengan elemen-elemen tersebut yang diletakan bersampingan, seperti layout kolom-kolom.

Properti `float` menerima beberapa nilai, yang paling popular adalah `left` dan `right`, yang akan membuat elemennya float ke kiri atau ke kanan dari elemen parent-nya.

```
img {
  float: left;
}
```

### Float dalam Latihan

Kita akan membuat layout halaman dengan header berada di atas, dua kolom di tengah-tengah, dan footer pada bagian bawah halaman. Pada elemen `<body>` dari halaman kita berisi kode HTML berikut:

``` html
<header>...</header>
<section>...</section>
<aside>...</aside>
<footer>...</footer>
```

Karena `<section>` dan `<aside>` merupakan elemen blok, maka kedua mereka akan bertumpuk satu dengan yang lain. Tetapi kita ingin mereka berada disamping satu dengan yang lain. Dengan membuat memberikan float pada `<section>` ke kiri dan `<aside>` ke kanan, maka kita dapat memposisikan mereka menjadi dua kolom yang saling bersebelahan. Berikut CSS-nya:

``` css
section {
  float: left;
}

aside {
  float: right;
}
```
Ketika elemen diberikan float, maka elemen tersebut akan float ke sisi dari elemen parentnya. Jika elemen tersebut tidak memiliki parent, maka elemen tersebut akan float ke sisi halaman.

Ketika kita memberikan float pada elemen, maka elemen tersebut keluar dari normal flow dokumen HTML. Akibatnya lebar dari elemen akan menjadi hanya selebar kontennya saja. Terkadang hal ini tidak diinginkan. Permasalahan ini bisa diatasi dengan cara memberikan nilai tetap pada properti `width` untuk setiap kolom. Kita juga gunakan properti margin untuk membuat antar elemen yang diberi float sehingga tidak saling berdempetan antara satu elemen dengan yang lain.

Kita tambahkan kode CSS sebelumnya menjadi berikut:

``` css
section {
  float: left;
  margin: 0 1.5%;
  width: 63%;
}

aside {
  float: right;
  margin: 0 1.5%;
  width: 30%;
}
```

<hr>

###### Float dapat Mengubah Nilai Display dari Elemen

Properti `float` bergantung pada nilai `display` `block`, dan akan mengubahnya menjadi `block` jika nilai `display`-nya bukan `block`. Akibatnya elemen `inline` yang diberikan float akan berubah menjadi `block` dan akan menerima `width` dan `height`.

<hr>

Dengan dua kolom, kita dapat memberikan float ke kiri pada satu elemen dan ke kanan pada elemen yang lain. Namun untuk tiga kolom kita harus menggunakan pendekatan yang berbeda. Misal HTML-nya seperti berikut:

``` html
<header>...</header>
<section>...</section>
<section>...</section>
<section>...</section>
<footer>...</footer>
```

Untuk memposisikan ketiga elemen `<section>` ini mejadi tiga kolom, maka kita akan memberikan float ke kiri untuk semua elemen ini dan kita juga akan mengubah lebarnya agar semua elemen ini dapat berdiri berdampingan. 

``` css
section {
  float: left;
  margin: 0 1.5%;
  width: 30%;
}
```

### Menghilangkan dan Memuat Float

Tujuan awal dari properti `float` yaitu konten dapat mengelilingi atau membungkus gambar. Walaupun bekerja sangat baik untuk gambar, tetapi `float` tidak dirancang untuk tujuan layout dan posisi, sehingga ada beberapa kekurangan.

Salah satu kekurangannya yaitu style tidak akan dirender dengan baik untuk elemen yang berdekatan dengan elemen yang diberikan float atau parent dari elemen float tersebut, karena elemen yang beri float akan keluar dari normal flow.

Sering nilai dari properti `margin` dan `padding` tidak diinterpretasi dengan benar, mengakibatkan menyatu dengan elemen float. Properti yang lain dapat kena dampak juga.

Kekurangan yang lainnya yaitu terkadang konten yang tidak diharapkan juga ikut mengisi mengililingi elemen float. Mengeluarkan elemen dari flow dokumen dapat membuat semua elemen disekitar elemen float untuk mengambil tempat yang ada dan mengelilingi elemen float tersebut, yang biasanya tidak diinginkan.

Pada contoh dua kolom sebelumnya, setelah kita memberikan float untuk elemen `<section>` dan `<aside>` dan sebelum kita memberikan lebar pada kedua elemen ini, konten dari elemen `<footer>` akan berada di antara elemen `<section>` dan `<aside>` mengisi tempat yang kosong.

Untuk menghindari hal ini, kita harus menghilangkan atau memuat float tersebut.

#### Menghilangkan Float

Menghilangkan float didapat dengan menggunakan properti `clear`, yang dapat menerima beberapa nilai: yang paling sering adalah `left`, `right`, dan `both`.

``` css
div {
  clear: left;
}
```

Nilai `left` akan menghilangkan float ke kiri, sedengkan `right` akan menghilangkan float ke kanan. Nilai `both` akan menghilangkan float ke kiri dan ke kanan, dan merupakan nilai yang paling ideal.

Kembali pada contoh sebelumnya, jika gunakan `clear` dengan nilai `both` pada elemen `<footer>` maka kita dapat menghilangkan float-nya. Penting untuk memberikan `clear` pada elemen setelah elemen yang diberi `float`, bukan sebelum, untuk mengembalikan normal flow.

``` css
footer {
  clear: both;
}
```

#### Memuat Float

Daripada menghilangkan float, cara lainnya yaitu dengan memuat float. Hasil dari kedua cara ini hampir sama, bedanya yaitu dengan memuat float ada jaminan bahwa style kita akan dirender dengan benar.

Untuk memuat float, elemen float harus berada di dalam elemen parent. Elemen parent akan bekerja sebagai tempat, yang akan membuat flow di luar elemen ini tetap normal. Berikut CSS untuk elemen parent, yang direpresentasikan dengan class `group`: 

``` css
.group:before, .group:after {
   content: "";
   display: table;
}

.group:after {
   clear: both;
}

.group {
   clear: both;
   /* zoom: 1; */
}
```

Banyak hal yang terjadi disini, tetapi intinya adalah CSS menghilangkan float pada elemen class `group` dan mengembalikan flow menjadi normal.

Lebih spesifik, pseudo elemen `:before` dan `:after` secara dinamik membangun elemen  di atas dan di bawah elemen class `group`. Elemen tersebut tidak memuat konten apapun dan ditampilkan sebagai elemen level `tabel`, seperti elemen level blok. Elemen yang dibangun secara dinamik setelah elemen class `group` akan menghilangkan float didalam elemen class `group`. Dan terakhir, elemen class `group` juga menghilangkan float yang ada di atas elemen ini, berjaga-jaga jika terdapat float kiri atau kanan.

Melihat contoh dua kolom sebelumnya, kita dapat membungkus elemen `<section>` dan `<aside>` dengan sebuah elemen parent. Elemen parent harus memuat float di dalamnya.

**HTML**

``` html
<header>...</header>
<div class="group">
  <section>...</section>
  <aside>...</aside>
</div>
<footer>...</footer>
```

**CSS**

``` css
.group:before,
.group:after {
  content: "";
  display: table;
}

.group:after {
  clear: both;
}

.group {
  clear: both;
  /* zoom: 1; */
}

section {
  float: left;
  margin: 0 1.5%;
  width: 63%;
}

aside {
  float: right;
  margin: 0 1.5%;
  width: 30%;
}
```

Teknik yang ditunjukan disini untuk memuat float disebut "clearfix" dan dapat ditemukan pada situs web lain dengan nama class `clearfix` atau `cf`.

## Mengatur Posisi dengan Inline-Blok

Cara lain selain float, kita dapat mengatur posisi konten dengan menggunakan properti `display` yang diberi nilai `inline-blok`.

Mengingat kembali nilai `inline-block` dari properti `display` akan menampilkan elemen dalam satu baris dengan membiarkan elemen tersebut menerima properti box model seperti `height`, `width`, `padding`, dan `margin`. Dengan menggunakan elemen inline-block kita dapat menggunakan box model tanpa perlu mengkhawatirkan menghilangkan float.

### Inline-Blok dalam Latihan

Kita gunakan kode HTML seperti pada contoh sebelumnya:

``` html
<header>...</header>
<section>...</section>
<section>...</section>
<section>...</section>
<footer>...</footer>
```

Sekarang kita ganti nilai `display` menjadi `inline-block`, dan menetapkan `margin` dan `width` seperti pada contoh sebelumnya:

``` css
section {
  display: inline-block;
  margin: 0 1.5%;
  width: 30%;
}
```

Sayangnya, kode ini sendiri tidak begitu berhasil, dan elemen `<section>` terakhir akan didorong ke baris baru. Hal ini karena elemen inline-block akan ditampilkan pada baris yang sama dengan yang lain, dan terdapat spasi kecil di antara mereka. Menjumlahkan semua `width` dan `margin` dan lebar dari spasi kecil tersebut akan membuat lebar totalnya menjadi lebih dari 100%, akibatnya elemen `<section>` yang terakhir akan berada pada baris baru. Untuk mengatasinya yaitu dengan cara menghilangkan spasi kecil tersebut.

### Menghilangkan Spasi di antara Elemen Inline-Blok

Ada beberapa cara untuk menghilangkan spasi kecil tersebut. Tapi kita akan fokus pada dua cara termudah, yang dilakukan di dalam HTML.

Solusi pertama yaitu menaruh tag pembuka dari elemen `<section>` yang baru satu baris dengan tag penutup dari elemen `<section>` yang sebelumnya. HTML-nya seperti berikut:

``` html
<header>...</header>
<section>
  ...
</section><section>
  ...
</section><section>
  ...
</section>
<footer>...</footer>
```

Menulis elemen inline-block seperti ini akan menjamin bahwa spasi di antara elemen tersebut akan hilang.

Cara yang lainnya yaitu dengan membuka komentar HTML langsung setelah tag penutup elemen inline-blok, lalu tutup komentar HTML langsung sebelum tag pembuka elemen inline-blok. Hasilnya akan sama seperti cara sebelumnya. Berikut HTML-nya:

``` html
<header>...</header>
<section>
  ...
</section><!--
--><section>
  ...
</section><!--
--><section>
  ...
 </section>
 <footer>...</footer>
```

## Membuat Layout yang Dapat Dipakai Ulang

Ketika membangun situs web, sebaiknya membuat style dan layout yang dapat dipakai di mana saja.

Pilihan yang terbaik untuk menggunakan elemen float atau inline-blok tergantung dari struktur halamannya. Saran gunakan elemen inline-blok untuk membuat grid, atau layout dari halaman, dan gunakan float ketika kita ingin membungkus konten dengan elemen yang lain (seperti membungkus gambar). Juga lebih mudah untuk bekerja dengan elemen inline-blok.

## Menempatkan Elemen Secara Unik

Jika kita ingin mengatur posisi elemen secara presisi, elemen float dan inline-blok akan susah untuk digunakan. Untuk situasi ini kita gunakan properti `position` yang dihubungkan dengan properti box offset.

Properti `position` mengidentifikasi bagaimana elemen akan ditempatkan pada halaman dan apakah akan berada pada normal flow dokumen. Properti ini digunakan bersamaan dengan properti box offset&mdash;`top`, `right`, `bottom`, dan `left`&mdash;yang akan mengidentifikasi dimana elemen akan diposisikan dengan memindahkan elemen pada arah yang berbeda.

Secara default, setiap elemen mempunyai nilai `position` `static`, yang artinya elemen tersebut berada pada normal flow dari dokumen dan tidak menerima properti box offset. Nilai ini akan diganti dengan `relative` atau `absolute`.

### Posisi Secara Relatif

Nilai `relative` untuk properti `position` membuat elemen tersebut muncul pada normal flow dari halaman, meninggalkan ruang dimana elemen tersebut berasal dan tidak membiarkan elemen lain mengisi ruang tersebut. Tetapi penampilan dari elemen ini dapat dimodifikasi dengan menggunakan properti box offset. Berikut contohnya:

**HTML**

``` html
<div>...</div>
<div class="offset">...</div>
<div>...</div>
```

**CSS**

``` css
div {
  height: 100px;
  width: 100px;
}

.offset {
  left: 20px;
  position: relative;
  top: 20px;
}
```

Elemen `<div>` kedua, elemen dengan class `offset`, mempunyai nilai `position` `relative` dan dua properti box offset, `left`  dan `top`. Elemen ini mengawetkan posisi awal, dan elemen lain tidak dapat berada ruang tersebut. Tambahan, properti box offset mengubah posisi elemen, ke kanan 20 pixel dengan properti `left` dan ke bawah 20 pixel dengan properti `top` dari posisi awal.

Ketika kita memposisikan elemen dengan menggunakan properti box offset, elemen tersebut akan menumpuk elemen yang lain, tidak seperti `margin` atau `padding` yang akan mendorong elemen lain.

### Posisi Secara Absolute

Berbeda dengan `relative`, properti `position` dengan nilai `absolute` tidak akan berada pada normal flow dokumen dan posisi awal elemennya tidak akan diwariskan.

Sebagai tambahan, elemen dengan nilai `absolute` akan diposisikan relatif terhadap parent. Jika tidak memiliki parent, maka elemen tersebut akan diposisikan relatif terhadap elemen `<body>`. Berikut contohnya:

**HTML**

``` html
<section>
  <div class="offset">...</div>
</section>
```

**CSS**

``` css
section {
  position: relative;
}

div {
  position: absolute;
  right: 20px;
  top: 20px;
}
```

Pada contoh ini, elemen `<section>` diposisikan secara relatif tapi tidak memuat properti box offset. Akibatnya posisinya tidak berubah. Elemen `<div>` dengan class `offset` memuat nilai `position` `absolute`. Karena elemen `<section>` adalah elemen parent yang paling dekat dengan elemen `<div>`, maka elemen `<div>` akan diposisikan relatif terhadap `<section>`.

Sebagai hasil dari properti box offset `right` dan `top`, elemen `<div>` akan muncul 20 pixel dari kanan dan 20 pixel dari atas.

## Rangkuman

Hal yang sudah dipelajari:
* Apa itu float dan cara menggunakannya untuk mengatur posisi konten
* Bagaimana cara menghilangkan dan memuat float
* Bagaimana cara memposisikan konten dengan menggunakan elemen inline-blok
* Bagaimana cara menghilangkan spasi kecil di antara elemen inline-blok
* Bagaimana cara memposisikan konten secara relatif dan absolut
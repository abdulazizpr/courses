<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Mengatur Latar Belakang &amp; Gradien

**Outline:**
* [Menambahkan Warna Latar Belakang](#1)
* [Menambahkan Gambar Latar Belakang](#2)
* [Merancang Latar Belakang Gradien](#3)
* [Menggunakan Banyak Gambar Latar Belakang](#4)
* [Menjelajahi Properti Baru Latar Belakang](#5)

Latar belakang mempunyai pengaruh yang signifikan pada desain dari situs web. Pada CSS, latar belakang elemen dapat berupa warna solid, gambar, gradien atau kombinasi dari ketiganya. Kita akan melihat bagaimana cara memilih latar belakang, termasuk gradien, pada elemen. Kita juga akan bermain dengan properti CSS3 untuk latar belakang.

<a name="1"></a>
## Menambahkan Warna Latar Belakang

Untuk menambahkan warna latar belakang dapat menggunakan properti `background` atau `background-color`. Properti `background` menerima warna dan gambar dalam versi pendek, sedangkan properti `background-color` hanya untuk mengatur warna solid saja.

``` css
div {
background-color: #b2b2b2;
}
```

Ketika kita menambahkan warna latar belakang, kita dapat menggunakan nilai kata kunci warna, kode heksadesimal, RGB, RGBa, HSL, dan HSLa. Yang paling sering digunakan adalah heksadesimal, namun untuk transparansi kita akan menggunakan RGBa atau HSLa.

<hr>

###### Latar Belakang Transparan

Ketika menggunakan nilai RGBa atau HSLa untuk memberi latar belakang transparan, sebaiknya siapkan warna cadangan karena tidak semua browser mendukung nilai RGBa dan HSLa. Masalah ini khusus terjadi pada Internet Explorer 8, untuk nilai yang tidak dia kenali, maka dia akan mengabaikannya.

Kita dapat mengatasi ini dengan memanfaatkan sifat kaskade dari CSS seperti berikut:

``` css
div {
  background-color: #b2b2b2;
  background-color: rgba(0, 0, 0, .3);
}
```

Karena RGBa ditulis terakhir, maka browser akan mencoba menampilkan warna tersebut. Jika tidak dapat ditampilkan, maka browser akan mencoba warna di atasnya.

<hr>

<a name="2"></a>
## Menambahkan Gambar Latar Belakang

Selain warna, kita juga bisa tambahkan gambar pada latar belakang. Untuk menambahkan gambar kita dapat menggunakan properti `backgroung` untuk menambahkan warna dan gambar sekaligus, atau menggunakan properti `background-image` untuk menambahkan gambar saja. Untuk merujuk sumber gambarnya kita harus menggunakan fungsi `url()`.

Inputan dari fungsi `url()` merupakan path dari gambarnya. Path ini ditulis di dalam tanda kurung dan diberi tanda petik.

``` css
div {
  background-image: url("alert.png");
}
```

Secara default, gambar yang ditambahkan pada latar belakang akan mengulang secara vertikal dan horizontal. Untuk mengatur hal ini, kita dapat menggunakan properti `background-repeat` dan `background-position`.

### Properti `background-repeat`

Properti `background-repeat` dapat digunakan untuk mengubah arah gambar akan berulang pada latar belakang.

``` css
div {
  background-image: url("alert.png");
  background-repeat: no-repeat;
}
```

Properti `background-repeat` menerima empat nilai: `repeat`, `repeat-x`, `repeat-y`, dan `no-repeat`. Nilai `repeat` merupakan nilai default dan akan membuat gambar latar belakang mengulang secara vertikal dan horizontal. Untuk nilai `repeat-x` akan mengulang gambar latar belakang secara horizontal, sedangkan `repeat-y` akan mengulang secara vertikal. Yann terakhir, nilai `no-repeat` akan membuat gambar hanya ditampilkan sekali tanpa perulangan.

### Properti `background-position`

Secara default, gambar latar belakang akan diletakan di sebelah kiri atas dari elemen. Dengan dengan menggunakan `background-position` kita dapat mengatur dimana kita meletakan gambar latar belakang relatif terhadap sudut tersebut.

``` css
div {
  background-image: url("alert.png");
  background-position: 20px 10px;
  background-repeat: no-repeat;
}
```

Properti `background-position` menerima dua nilai: geseran horizontal dan geseran vertikal. Jika kita hanya menggunakan satu nilai, maka nilai tersebut akan digunakan untuk geseran horizontal, sedangkan geseran vertikal akan berniali `50%`.

Karena kita memindahkan gambar latar belakang dari kiri atas elemen, maka nilai masukkan harus berhubungan sudut tersebut.

Untuk mengatur nilai `background-position` kita dapat menggunakan kata kunci `top`, `right`, `bottom`, `left`, dan `center`, pixel, persentase, atau ukuran panjang lainnya. Kata kunci dan persentase bekerja serupa satu dengan yang lain. Nilai `left` `top` akan sama dengan nilai `0` `0`  akan membuat gambar akan berada pada kiri atas elemen. Sedankan nilai `right` `bottom` akan sama dengan `100%` `100%` akan meletakkan posisi gambar pada sudut kanan bawah elemen.

![](http://learn.shayhowe.com/assets/images/courses/html-css/setting-backgrounds-and-gradients/background-position.png)

Menggunakan pixel juga umum digunakan karena dapat memberikan presisi dalam meletakan gambar.

### Versi Pendek untuk Gambar Latar Belakang

Properti `background-color`, `background-image`, `background-position`, dan `background-repeat` dapat dikumpulkan dalam satu properti, yaitu `background`. Urutan pada properti dapat berubah-ubah tetapi biasanya `background-color`, `background-image`, `background-position`, dan terakhir `background-repeat`. 

``` css
div {
  background: #b2b2b2 url("alert.png") 20px 10px no-repeat;
}
```

### Contoh Gambar Latar Belakang

Pada contoh berikut, kita akan menggunakan properti `background` dengan nilai versi pendek dari `background-color`, `background-image`, `background-position`, dan `background-repaet`.

Perhatikan bahwa terdapat nilai relatif dan nilai absolut pada properti `background-position`. Nilai pertama, 20 pixel, adalah nilai horizontal, meletakkan gambar 20 pixel dari kiri elemen. Nilai kedua, `50%`, adalah nilai vertikal yang akan meletakkan gambarnya pada tengah-tengah elemen secara vertikal.

Properti dan nilai ditambahkan untuk menambahkan style.

**HTML**

``` html
<div class="notice-success">
  Woo hoo! Congratulations, you did it!
</div>
```

**CSS**

``` css
.notice-success {
  background: #67b11c url("tick.png") 20px 50% no-repeat;
  border: 2px solid #467813;
  border-radius: 5px;
  color: #fff;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  padding: 15px 20px 15px 50px;
}
```

<a name="3"></a>
## Merancang Latar Belakang Gradien

Latar belakang gradien diperkenalkan pada CSS3. Walaupun tidak didukung oleh browser lama, semua browser mendukung latar belakang gradien.

Pada CSS, latar belakang gradien diperlakukan sebagai latar belakang. Kita dapat membuat gradien dengan menggunakan properti `background` atau `background-image` sama seperti gambar latar belakang biasa. Nilai dari properti latar belakang gradien bervariasi tergantung dari tipe yang kita inginkan, linier atau radial.

### Latar Belakang Gradien Linier

Dahulu, para desainer dan developer harus memotong gambar gradien, yang dibuat oleh software image-processing, dan menggunakannya sebagai latar belakang gradien dari elemen. Hal ini berhasil, tapi memerlukan proses yang panjang dan lama. Sekarang latar belakang gradien linier dapat dilakukan dalam CSS, tidak perlu membuat gambar baru lagi.

``` css
div {
  background: #466368;
  background: -webkit-linear-gradient(#648880, #293f50);
  background:    -moz-linear-gradient(#648880, #293f50);
  background:         linear-gradient(#648880, #293f50);
}
```

Gradien linier dapat dibuat dengan menggunakan funsi `linier-gradient()` pada properti `background` atau `background-image`. Inputan dari fungsi ini adalah dua nilai warna, warna yang pertama adalah warna awal dan warna yang kedua adalah warna akhir. Browser akan mengurus warna transisi di antaranya.

Sebelum kita menggunakan latar belakang gradien, kita harus menyiapkan warna solid cadangan untuk mengantisipasi jika browser tidak dapat menampilkan latar belakang gradien.

### Mengubah Arah dari Latar Belakang Gradien

Secara default, latar belakang linier akan bergerak dari atas ke bawah dari elemen, transisi warna dari warna pertama ke warna kedua. Namun, arahnya dapat kita ubah dengan menggunakan nilai derajat sebelum nilai warna.

Sebagai contoh, jika kita ingin gradien dari kiri ke kanan elemen maka kita dapat menggunakan kata kunci `right`. Kata kunci juga dapat dikombinasikan. Jika kita ingin gradiennya bergerak dari kiri atas ke kanan bawah, kita dapat menggunakan kata kunci `to right bottom`.

``` css
div {
  background: #466368;
  background: linear-gradient(to right bottom, #648880, #293f50);
}
```

Ketika kita menggunakan gradien diagonal pada elemen yang bukan kotak, maka gradiennya tidak akan berjalan dari tepat satu sudut ke sudut yang lain. Tetapi, garis transisinya akan berada dari sudut-sudut yang tegak lurus dengan sudut awal, dan gradiennya akan bergerak dari sudut awal ke sudut akhir tegak lurus dengan garis transisi.

![](http://meyerweb.com/pix/2012/04gradients03.gif)

Selain kata kunci, nilai derajat juga diperbolehkan. Jika kita ingin gradiennya bergerak ke kiri atas elemen, maka kita bisa gunakan nilai `315deg`, atau jika kita ingin gradiennya ke kanan bawah maka kita bisa gunakan nilai `135deg`.

### Latar Belakang Radial

Terkadang kita menginginkan gradien berbentuk lingkaran. Latar belakang gradien radial bekerja sama seperti gradien linier. Tetapi kita gunakan fungsi `radial-gradient()`.

``` css
div {
  background: #466368;
  background: radial-gradient(#648880, #293f50);
}
```

Gradien radial bekerja dari dalam ke luar elemen. Nilai warna pertama dari fungsi `radial-gradient()` akan berada pada titik tengah dari elemen, dan warna kedua akan berada pada luar elemen. Browser akan membuat transisi warna dari kedua warna tersebut.

Perbedaan utama antara gradien linier dan radial adalah gradien radial cukup kompleks, dengan nilai untuk lokasi, ukuran, radius, dan lainnya.

### Pemberhentian Warna Gradien

Untuk dasarnya, latar belakang gradien akan bertransisi dari satu warna ke warna lainnya. Namun kita bisa menambahkan warna baru ke gradiennya dan membiarkan browser membuat transisi dari semua warna tersebut. Untuk melakukannya, kita tambahkan pemberhentian warna ke fungsi gradien.

``` css
div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880, #293f50);
}
```

Secara default, browser akan menempatkan setiap pemberhentian warna pada jarak yang sama antara setiap pemberhentian dan akan membuat transisi warna. Kita juga dapat meletakan lokasi dimana pemberhentian warna diletakan. Lokasinya harus dideklarasikan sebagai nilai panjang dan berada setelah nilai warna.

``` css
div {
  background: #648880;
  background: linear-gradient(to right, #f6f1d3, #648880 85%, #293f50);
}
```

Jika tidak didefinisikan, warna pertama akan berada pada `0%` dan warna terakhir akan berada pada `100%`.

### Contoh Latar Belakang Gradien

Menggunakan contoh yang sebelumnya, akan kita ganti latar belakangnya menjadi latar belakang gradien linier.

Untuk itu kita memerlukan dua properti `background`. Yang pertama menetapkan warna solid heksadesimal, yang berfungsi sebagai cadangan jika browser tidak mendukung latar belakang gradien. Properti `background` yang kedua memuat fungsi `linear-gradient()`, yang mendefinisikan gradien hijau dari atas ke bawah elemen.

**HTML**

``` html
<div class="notice-success">
  Woo hoo! Congratulations, you did it!
</div>
```

``` css
.notice-success {
  background: #67b11c;
  background: linear-gradient(#72c41f, #5c9e19);
  border: 2px solid #467813;
  border-radius: 5px;
  color: #fff;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  padding: 15px 20px;
}
```

<a name="4"></a>
## Menggunakan Banyak Gambar Latar Belakang

Pada waktu yang lama, elemen hanya bisa memiliki satu gambar latar belakang. Namun dengan CSS3 kita diperbolehkan untuk menggunakan lebih dari satu gambar latar belakang yang dipisahkan dengan koma.

Gambar latar belakang yang pertama akan berada diatas tumpukan gambar, sedangkan gambar latar yang ditulis di akhir akan berada pada bawah tumpukan gambar. Nilai di antaranya akan menumpuk menyesuaikan.

``` css
div {
  background:  url("foreground.png") 0 0 no-repeat, url("middle-ground.png") 0 0 no-repeat, url("background.png") 0 0 no-repeat;
}
```

Kode ini menggunakan nilai versi pendek dan beberapa nilai gambar latar belakang. Nilai-nilai dapat dipecah menjadi versi panjang dengan memberi nilai pada properti `background-image`, `background-position`, dan `background-repeat`.

### Contoh Gambar Latar Belakang Ganda

Kembali kepada contoh sebelumnya. Akan kita tambahkan, gambar latar belakang tanda ceklis pada latar belakang gradiennya.

**HTML**

``` html
<div class="notice-success">
  Woo hoo! Congratulations, you did it!
</div>
```

**CSS**

``` css
.notice-success {
  background: #67b11c;
  background: url("tick.png") 20px 50% no-repeat, linear-gradient(#72c41f, #5c9e19);
  border: 2px solid #467813;
  border-radius: 5px;
  color: #fff;
  font-family: "Helvetica Neue", Helvetica, Arial, sans-serif;
  padding: 15px 20px 15px 50px;
}
```

<a name="5"></a>
## Menjelajahi Properti Baru Latar Belakang

Beberapa propreti baru dari CSS adalah: `background-size`, `background-clip`, dan `background-origin`.

Properti `background-size` membuat kita dapat mengubah ukuran dari gambar latar belakang. Sedangkan properti `background-clip` mengatur dimana gambar latar belakang akan di-crop, dan properti `background-origin` mengatur dimana gambar latar belakang akan dimuat dalam sebuah elemen (contohnya di dalam border, atau di dalam padding)

### Ukuran Latar Belakang CSS3

Properti `background-size` mengatur ukuran dari gambar latar belakang. Properti ini menerima beberapa nilai, termasuk panjang dan kata kunci.

Ketika menggunakan nilai panjang, kita dapat menentukan lebar dan tinggi dengan menggunakan dua nilai yang dipisahkan oleh spasi. Nilai pertama akan menentukan lebar gambar latar belakang. Sedangkan nilai kedua akan menentukan tinggi dari gambar latar belakang. Perhatikan bahwa nilai persentase berelasi dengan ukuran elemen, bukan ukuran asli gambar latar belakang.

Jika kita menetapkan nilai dari properti `background--size` menjadi `100%` maka gambar latar belakang akan memuat lebar elemen. Jika nilai kedua tidak ditentukan, maka tingginya akan menyesuaikan rasio dari gambar latar belakang.

Kata kunci `auto` digunakan untuk menjaga rasio dari gambar latar belakang. Sebagai contohnya, jika kita ingin menentukan tinggi dari gambar latar belakang menjadi `75%` tinggi dari elemen dan ingin tetap menjaga rasio dari gambar, maka nilai width-nya harus `auto`.

``` css
div {
  background: url("shay.jpg") 0 0 no-repeat;
  background-size: auto 75%;
  border: 2px dashed #9799a7;
  height: 240px;
  width: 200px;
}
```

### Nilai Kata Kunci `cover` &amp; `contain`

Sebagai tambahan untuk nilai dari properti `background-size`, ada `cover` dan `contain`.

Nilai `cover` digunakan untuk mengisi semua latar belakang elemen dengan menjaga rasio dari gambarnya. Karena rasionya terjaga maka gambarnya akan terpotong untuk menyesuaikan dengan ukuran elemennya.

Nilai kata kunci `contain` akan juga mengisi latar belakang dengan menjaga rasio dari gambarnya. Bedanya jika `cover` akan memilih sisi terpendek dari gambar yang digunakan sebagai patokan, `contain` akan menggunakan sisi terpanjang sebagai patokan sehingga gambarnya akan tetap utuh pada elemen tersebut.

### CSS3 `background-clip` &amp; `background-origin`

Properti `background-clip` digunakan untuk menentukan area yang akan di-cover oleh gambar latar belakang. Sedangkan properti `background-origin` menentukan posisi origin dari properti `background-position`. Nilai yang bisa diterima dari properti ini adalah: `border-box`, `padding-box`, dan `content-box`. 

``` css
div {
  background: url("shay.jpg") 0 0 no-repeat;
  background-clip: padding-box;
  background-origin: border-box;
}
```

Nilai dari properti `backgroundclip` adalah `border-box` secara default, membuat gambar latar belakang mengikuti border. Sedangkan nilai dari `background-origin` adalah `padding-box` secara defaul, membuat gambar latar belakang dapat melebar sampai padding dari elemen.

## Rangkuman

Hal yang sudah dipelajari:
* Bagaimana cara menambahkan warna dan gambar latar belakang pada elemen
* Gradien CSS, baik linier ataupun radial, dan cara mengaturnya
* Bagaimana cara untuk menerapkan beberapa gambar latar belakang pada satu elemen
* Properti baru CSS3 yang dapat mengubah ukuran, area dan origin dari gambar latar belakang
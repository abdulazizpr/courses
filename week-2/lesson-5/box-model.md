<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Box Model

**Outline:**
* Menampilkan Elemen
* Box Model
* Developer Tools

## Menampilkan Elemen

Elemen level blok memiliki lebarnya sendiri tidak tergantung dari konten, dan dimulai dari baris baru. Elemen level blok biasanya untuk konten yang besar seperti heading atau elemen struktural.

Elemen level inline mengambil lebar hanya selebar kontennya saja dan berada pada baris yang sama dengan elemen level inline lainnya. Elemen level inline biasanya untuk konten yang lebih kecil seperti beberapa yang dicetak tebal atau cetak miring.

### Display

Bagaimana elemen ditampilkan bergantung dari properti `display`. Nilai yang umum untuk `display` adalah `block`, `inline`, `inline-block`, dan `none`. Nilai `block` akan mengubah elemen tersebut akan menjadi elemen level blok.

``` css
p {
	display: block;
}
```

Begitu juga `inline` akan mengubah elemen tersebut menjadi level inline.

``` css
p {
	display: inline;
}
```

Yang menarik adalah nilai `inline-block`. Elemen dengan nilai `inline-block` akan seperti elemen level blok, memenuhi sifat-sifat box model, tetapi elemen ini akan ditampilkan satu baris dengan elemen yang lainnya.

``` css
p {
	display: inline-block;
}
```

<hr>

###### Spasi antara Elemen Inline-Blok

Elemen inline-blok tidak selalu ditampilkan menempel atau ditampilkan langsung antara satu elemen dengan yang lainnya. Biasanya terdapat spasi kecil di antara kedua elemen tersebut.

<hr>

Yang terakhir yaitu nilai `none` akan menyembunyikan elemen dan menganggap elemen tersebut tidak ada. Elemen yang berada di dalam elemen ini juga akan disembunyikan.

``` css
div {
  display: none;
}
```

## Box Model

Berdasarkan konsep [box model](http://css-tricks.com/the-css-box-model/), **setiap elemen pada halaman merupakan kotak persegi panjang** yang memiliki lebar, tinggi, padding, border, dan margin.

![http://www.w3.org/TR/CSS2/images/boxdim.png](http://www.w3.org/TR/CSS2/images/boxdim.png)

Lebar dan tinggi dari kontennya dapat didefinisikan dari properti `display` atau dari properti `width` dan `height` elemennya. `padding` dan `border` memperluas dimensi dari persegi panjangnya ke luar dari lebar dan tinggi elemennya. Terakhir, `margin` yang kita tentukan akan mengikuti bordernya. **Contoh:**

``` css
div {
  border: 6px solid #949599;
  height: 100px;
  margin: 20px;
  padding: 20px;
  width: 400px;
}
```

Berdasarkan box model, lebar total dari suatu elemen dapat dihitung dengan menggunakan rumus berikut:

```
margin-right + border-right + padding-right + width + padding-left + border-left + margin-left
```

Sedangkan untuk total tingginya dapat dihitung dengan menggunakan rumus:

```
margin-top + border-top + padding-top + height + padding-bottom + border-bottom + margin-bottom
```

Dengan menggunakan rumus yang ada di atas, kita dapat menghitung lebar total dan tinggi total pada contoh kita diatas:

__Lebar:__ `492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px`

__Tinggi:__ `192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px`

### Lebar &amp; Tinggi

Setiap elemen mempunyai lebar dan tinggi secara default. Mungkin 0 pixel, tetapi browser secara default akan memberi ukuran pada setiap elemen.

#### Lebar

Lebar secara default dari elemen tergantung pada nilai `display`. Elemen level blok secara default memiliki lebar `100%` mengisi tempat yang ada secara horizotal. Elemen level inline dan inline-blok akan memiliki lebar selebar kontennya. Elemen level inline tidak meiliki ukuran yang tetap, jadi properti `width` dan `height` hanya untuk elemen non-inline. **Contoh:**

``` css
div {
  width: 400px;
}
```

#### Tinggi

Secara default, tinggi dari elemen tergantung dari kontennya. Elemen akan menyesuaikan secara vertikal sesuai dengan timggi kontennya. **Contoh:**

``` css
div {
  height: 100px;
}
```

<hr>

###### Mengubah Ukuran Elemen Level Inline

Ingat bahwa elemen level inline tidak menerima properti `width` dan `height` dan nilai yang bersesuaian. Tetapi elemen level blok dan inline-blok akan menerima properti `width` dan `height` dan nilai yang bersesuaian.

<hr>

### Margin & Padding

Tergantung dari elemennya, browser akan memberikan margin dan padding secara default untuk keterbacaan dan kejelasan. Umumnya kita menjumpai hal ini pada elemen berbasis teks. Default margin dan padding akan berbeda dari satu browser ke browser yang lainnya.

#### Margin

Properti `margin` menentukan ruang kosong disekitar elemen tersebut. Margin berada di luar border dan memiliki warna yang transparan. Margin dapat digunakan untuk menentukan posisi elemen pada halaman. Atau menentukan jarak ke elemen yang lainnya. **Contoh:**

``` css
div {
  margin: 20px;
}
```

Margin secara vertikal dari properti `margin` yaitu `top` dan `bottom` tidak diterima oleh elemen level inline. Tetapi diterima oleh elemen level blok dan inline blok.

#### Padding

Properti `padding` sangat mirip dengan properti `margin`; perbedaannya yaitu padding berada di dalam border elemen. Properti `padding` digunakan untuk membuat spasi secara langsung di dalam elemen. **Contoh:**

``` css
div {
  padding: 20px;
}
```

Properti `padding`, tidak seperti properti `margin`, akan bekerja secara vertikal untuk elemen level inline. Padding secara vertikal ini akan menyatu dengan baris diatas atau dibawahnya, tetapi akan ditampilkan.

<hr>

###### Margin &amp; Padding pada Elemen Level Inline

Elemen level inline bekerja sedikit berbeda dengan elemen blok dan inline-blok untuk margin dan padding. Margin hanya bekerja secara horizontal&mdash;`left` dan `right`&mdash;pada elemen level inline. Padding bekerja untuk setiap sisi dari elemen level inline, tetapi `padding` secara vertikal&mdash;`top` dan `bottom`&mdash;akan menyatu dengan baris diatas dan dibawah dari elemen tersebut.

Margin dan padding bekerja secara normal untuk elemen blok dan inline-blok. 

<hr>

#### Deklarasi Margin &amp; Padding

Pada CSS terdapat lebih dari satu cara untuk mendeklarasi nilai dari suatu properti. Kita dapat menggunakan versi panjang, mendefinisikan satu-satu setiap properti secara terpisah. Atau kita dapat menggunakan versi singkat, mendefinisikan semua nilainya hanya pada satu properti. Tidak semua properti mempunyai versi pendeknya.

Properti `margin` dan `padding` memiliki versi panjang dan versi pendek. Untuk mendefinisikan nilai yang sama untuk semua sisi, maka kita berikan satu nilai.

``` css
div {
  margin: 20px;
}
```

Jika kita ingin memberikan satu nilai untuk `top` dan `bottom` dan nilai yang lainnya untuk `left` dan `right` dari elemennya, maka kita berikan dua nilai: nilai yang pertama untuk `top` dan `bottom`, kemudian nilai untuk `left` dan `right`. Berikut kita berikan margin 10 pixel untuk `top` dan `bottom`, dan margin 20 pixel untuk `left` dan `right`.

``` css
div {
  margin: 10px 20px;
}
```

Untuk memberikan nilai untuk masing-masing sisi, maka kita berikan nilai tersebut secara berurutan dari `top`, `right`, `bottom`, dan `left`, bergerak searah jarum jam. Berikut kita berikan margin 10 pixel untuk `top`, 20 pixel untuk `right`, 0 pixel untuk `bottom` dan 15 pixel untuk `left`.

``` css
div {
  margin: 10px 20px 0 15px;
}
```

Dengan menggunakan properti `margin` atau `padding` dan diikuti dengan jumlah nilai yang berbeda-beda, maka ini disebut versi singkat. Untuk versi panjang, kita dapat memberikan nilai untuk satu sisi saja dengan menggunakan satu properti. Propertinya yaitu nama properti (dalam hal ini `margin` atau `padding`) yang diikuti oleh tanda kurang `-` dan sisi yang ingin kita beri nilai: `top`, `right`, `bottom`, atau `left`. Contoh:
``` css
div {
  margin-top: 10px;
  padding-left: 6px;
}
```
<hr>

###### Warna Margin &amp; Padding

Properti `margin` dan `padding` benar-benar transparan dan tidak menerima nilai warna apapun. Walaupun transparan, mereka akan menampilkan warna latar belakang dari elemen yang terkait. Untuk margin, kita akan melihat warna latar dari elemen parent, dan untuk padding kita akan melihat warna latar untuk elemen tersebut.

<hr>

### Border

Border berada di antara padding dan margin, memberikan garis batas di sekitar elemen. Properti `border` menerima tiga nilai: `width`, `style`, dan `color`. Versi Singkat dari properti `border` terdiri dari urutan tersebut&mdash;`width`, `style`, `color`. Pada versi panjang, tiga nilai ini dapat dipecah menjadi properti `border-width`, `border-style`, dan `border-color`.

Border memiliki beberapa penampilan. Style yang paling umum digunakan adalah `solid`, `double`, `dashed`, `dotted`, dan `none`, tetapi masih ada pilihan yang lainnya. **Contoh:**

``` css
div {
  border: 6px solid #949599;
}
```

#### Sisi Border secara Individual

Seperti properti `margin` dan `padding`, border dapat diletakan pada satu sisi saja. Kita memerlukan properti: `border-top`, `border-right`, `border-bottom`, dan `border-left`. Nilai dari properti ini sama dengan properti `border` itu sendiri: `width`, `style`, dan `color`. Kita ingin memberikan border hanya pada sisi bawah:

``` css
div {
  border-bottom: 6px solid #949599;
}
```

Sebagai tambahan, style dari satu sisi border dapat dikendalikan tersendiri. Kita ingin mengganti lebar border bagian bawah:

``` css
div {
  border-bottom-width: 12px;
}
```

#### Jari-Jari Border

Properti `border-radius` dapat membuat sudut dari elemen menjadi melengkung. Properti `border-radius` menerima unit panjang, termasuk persentase dan pixel, yang akan menentukan jari-jari dari sudut elemen  yang akan dilengkungkan. Satu nilai akan melengkungkan semua sudut. Dua nilai akan melengkungkan `top-left`/`bottom-right` dan `top-right`/`bottom-left` sesuai urutan tersebut. Empat nilai akan melengkungkan `top-left`, `top-right`, `bottom-right`, dan `bottom-left` sesuai urutan tersebut, searah jarum jam.

``` css
div {
  border-radius: 5px;
}
```

Properti `border-radius` dapat dipecah menjadi properti versi panjang untuk mengganti jari-jari dari sudut tertentu. Properti versi panjang ini dimulai dari `border`, kemudian diikuti oleh sudut lokasi vertikal (`top` atau `bottom`) dan sudut lokasi horizontal (`left` atau `right`), dan diakhiri dengan `radius`. Kita ganti jari-jari dari sudut kanan atas:

``` css
div {
  border-top-right-radius: 5px;
}
```

### Mengubah Ukuran Box

Box model, dapat diubah untuk memberikan perhitungan yang berbeda. CSS3 memperkenalkan properti `box-sizing`, yang memberikan kita pilihan bagaimana box model bekerja dan menghitung ukuran elemennya. Properti ini menerima tiga nilai, yaitu `content-box`, `padding-box`, dan `border-box`.

#### Nilai `content-box`

Nilai `content-box` merupakan nilai default. Ukuran dari elemennya adalah penjumlahan dari `width` atau `height`, lalu `padding`, `border`, dan juga `margin`.

``` css
div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}
```

<hr>

###### Properties &amp; Nilai Sesuai Browser

<hr>

#### Nilai `padding-box`

Nilai `padding-box` mengikutsertakan nilai dari `padding` pada `width` dan `height` dari elemen tersebut. Ketika menggunakan nilai `padding-box`, elemen yang memiliki `width` 400 pixel dan `padding` 20 pixel akan tetap mempunyai lebar sebesar 400 pixel. Untuk nilai `padding` yang semakin besar maka ukuran konten akan menyusut untuk menyesuaikan dengan lebarnya.

Jika kita tambahkan `border` dan `margin`, nilai tersebut akan ditambahkan dengan properti `width` atau `height` untuk menghitung ukuran box secara penuh. Sebagai contoh jika kita tambahkan `border` 10 pixel dan `padding` 20 pixel di setiap sisi dari elemen yang memiliki `width` 400 pixel, maka lebar total yang sebenarnya adalah 420 pixel.

``` css
div {
  box-sizing: padding-box;
}
```

#### Nilai `border-box`

Nilai `border-box` membuat nilai dari properti `border` dan `padding` termasuk dalam `width` dan `height` dari elemen tersebut. Ketika menggunakan nilai `border-box`, jika sebuah elemen memiliki `width` 400 pixel, `padding` 20 pixel untuk setiap sisi, dan `border` 10 pixel untuk setiap sisi, maka lebar dari elemen tersebut akan tetap 400 pixel.

Nilai dari `margin` harus ditambahkan untuk menghitung lebar total dari elemen tersebut jika kita menambahkan margin.

``` css
div {
  box-sizing: border-box;
}
```

#### Memilih Box Size

Secara umum, nilai dari `box-sizing` yang terbaik adalah `border-box`, karena ukuran elemennya akan tetap untuk berapapun nilai `padding` dan `border`. Termasuk jika menetapkan `width` dengan menggunakan persentase, maka ukurannya akan tetap.

Kekurangannya hanya properti `box-sizing` belum didukung oleh semua browser, terutama untuk browser yang tua. Tetapi hal tersebut dapat teratasi dengan adanya update dari browser-browser tersebut.

## Developer Tools

Hampir semua browser memiliki _Developer Tools_. Dengan tools ini, kita dapat melihat elemen HTML yang ada di suatu halaman, dan melihat properti CSS yang dikenakan. Tools ini juga mengikutsertakan diagram box model untuk menampilkan perhitungan ukuran dari suatu elemen.

Untuk melihat Developer Tools pada Google Chrome, klik "view" pada menu bar, kemudian pilih "Developer" lalu "Developer Tools."

Klik pada kaca pembesar membuat kita dapat memilih elemen yang ada pada halaman untuk melihat informasi yang ada pada elemen tersebut.

Setelah memilih elemen, pilih "Computed" pada panel bagian kanan. Maka akan ditampilkan box model dari elemen tersebut.

![](http://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/developer-tools.png)

## Rangkuman

Hal yang sudah dipelajari:
* Tampilan dari elemen
* Apa itu box model dan mengapa penting
* Mengubah ukuran, termasuk tinggi dan lebar dari elemen
* Menambahkan margin, padding, dan border pada elemen
* Mengubah box sizing dari elemen dan efeknya pada box model
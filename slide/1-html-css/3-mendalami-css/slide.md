<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Mengenal CSS

---
<!-- page_number: true -->
<!-- *template: invert -->
## Kaskade

---

Semua style css pada stylesheet bersifat *kaskade* sehingga style dapat ditambahkan atau ditimpa tanpa perlu menghapus kode stylenya.

**Contoh**: Pada bagian atas stylesheet, kita memilih semua elemen paragraf dan mengubah warna latar belakangnya menjadi `orange` dan ukuran tulisannya menjadi `24px`. Kemudian pada bagian bawah stylesheet, kita pilih semua elemen paragraf dan mengubah warna latar belakangnya menjadi `green`.

---

``` css
p {
  background: orange;
  font-size: 24px;
}

p {
  background: green;
}
```

Karena selektor paragraf yang mengubah warna latar belakang menjadi `green` berada setelah selektor paragraf yang mengubah warna latar belakang menjadi `orange`, maka yang terakhir yang dipilih. 

---

Semua latar belakang paragraf akan berwarna `green`. Sedangkan untuk ukuran tulisannya akan tetap berukuran `24px` karena selektor yang kedua tidak mengubah ukuran tulisan.

---

### Kaskade pada Properti

Semua properti dalam satu selektor juga bersifat kaskade. 

**Contoh**: Kita pilih semua elemen paragraf dan mengubah warna latar belakangnya menjadi `orange`. Kemudian di bawah deklarasi tersebut kita berikan deklarasi lagi untuk mengubah warna latar belakangnya menjadi `green`.

``` css
p {
  background: orange;
  background: green;
}
```

---

Karena deklarasi mengubah warna latar belakang menjadi `green` berada setelah deklarasi mengubah warna latar belakang menjadi `orange`, maka semua paragraf akan memiliki warna latar belakang `green`.

---
<!-- *template: invert -->
## Menghitung Spesifisitas

---

Setiap selektor pada CSS mempunyai berat spesifisitas. Berat spesifisitas selektor dan juga penempatannya pada stylesheet akan menentukan hasil dari style.

Selektor tipe memiliki berat spesifitas yang rendah, yaitu `0-0-1`. 
Selektor class memiliki berat spesifitas yang sedang, yaitu `0-1-0`. 
Terakhir, Selektor ID memiliki berat spesifitas yang tinggi, yaitu `1-0-0`.

---

Semakin tinggi berat spesifisitas selektor maka semakin tinggi superioritas dari selektor tersebut jika terjadi konflik. 

**Contoh**: Jika elemen paragraf dipilih menggunakan selektor tipe di satu tempat dan di tempat lain dipilih menggunakan selektor ID, maka selektor ID akan memiliki hak yang lebih tinggi tidak tergantung tempat selektor ID itu berada.

HTML
``` html
<p id="makanan">...</p>
```

---

CSS
``` css
#makanan {
  background: green;
}

p {
  background: orange;
}
```

Kita mempunyai elemen paragraf dengan ID  `makanan`. Pada CSS, elemen paragraf tersebut dipilih dengan menggunakan dua selektor berbeda: satu selektor tipe dan satu selektor ID. 

---

Walaupun selektor tipe berada di bawah selektor ID, tetapi selektor ID memiliki hak yang lebih tinggi karena dia memiliki berat spesifisitas yang lebih tinggi. Akibatnya paragraf tersebut akan berwarna `green`.

----
<!-- *template: invert -->
## Menggabungkan Selektor

---

Dengan menggabungkan selektor maka kita dapat memilih lebih spesifik elemen atau grup elemen yang akan kita beri style.

**Contoh**: Kita ingin memilih semua elemen paragraf dengan class `hotdog` dan mengganti warna latar belakangnya menjadi `brown`. Tetapi ada satu paragraf dengan class `mustard` yang ingin kita ganti warna latar belakangnya menjadi `yellow`.

---

HTML
``` html
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

CSS
``` css
.hotdog p {
  background: brown;
}

.hotdog p.mustard {
  background: yellow;
}
```

---

Selektor yang digabungkan harus dibaca dari kanan ke kiri. Selektor paling kanan dekat tanda kurung kurawal disebut *selektor kunci*.


Selektor gabungan pertama adalah `.hotdog p` memuat dua selektor: selektor class `hotdog` dan selektor type `p`. Kedua selektor ini dipisahkan oleh spasi. Selektor kuncinya adalah selektor tipe `p`. Selektor gabungan ini akan memilih elemen paragraf yang berada di dalam elemen dengan atribut class `hotdog`.

---

Selektor yang kedua adalah `.hotdog p.mustard` memuat tiga selektor: dua selektor class `hotdog` dan `mustard`, dan satu selektor tipe `p`. Untuk selektor ini, selektor kuncinya adalah selektor class `mustard`. Maka selektor gabungan ini akan memilih elemen paragraf dengan class `mustard` yang berada di dalam elemen dengan class `hotdog`.

Perhatikan jika kita beri spasi antara selektor tipe `p` dan selektor class `mustard`, maka selektor gabungan tersebut akan menunjuk elemen yang lain, yaitu elemen dengan class `mustard` yang berada di dalam elemen paragraf yang berada di dalam elemen dengan class `hotdog`.

---

### Spesifisitas Selektor Gabungan

Ketika selektor digabungkan, bagitu juga dengan berat spesifisitas selektornya. Menghitungnya yaitu dengan cara menjumlahkan semua masing-masing berat selektornya.

**Contoh:** Selektor `.hotdog p` memiliki berat `0-1-1` karena terdapat `1` selektor class dan `1` selektor tipe.
Sedangkan selektor `.hotdog p.mustard` memiliki berat `0-2-1` karena terdapat `2` selektor class dan `1` selektor tipe.

---

Dengan membandingkan berat spesifitas dari kedua selektor gabungan tersebut, maka selektor kedua yang akan memiliki superioritas lebih tinggi. Sehingga jika kita pindahkan selektor gabungan kedua ke atas selektor gabungan yang pertama maka tidak akan mempengaruhi style sama sekali.
``` css
.hotdog p.mustard {
  background: yellow;
}

.hotdog p {
  background: brown;
}
```

---
<!-- *template: invert -->
## Memberikan Style Berlapis dengan Class Majemuk

---

Salah satu cara untuk menjaga agar berat spesifitas dari selektor kita tetap rendah, berbagi style antara satu elemen dengan elemen yang lainnya, yaitu dengan cara menggunakan class majemuk.

Elemen HTML dapat memiliki nilai lebih dari satu dengan cara memisahkannya dengan spasi.

**Contoh**: Kita ingin ukuran tulisan pada semua tombol kita berukuran `16px`, namun kita menginginkan warna latar belakang dari tombol kita berbeda tergantung tombol yang digunakan.

---

HTML
``` html
<a class="btn btn-danger">...</a>
<a class="btn btn-success">...</a>
```

CSS
``` css
.btn {
  font-size: 16px;
}
.btn-danger {
  background: red;
}
.btn-success {
  background: green;
}
```

---

Disini kita punya dua elemen link, dengan class majemuk. Class pertama yaitu `btn` digunakan untuk mengubah ukuran tulisan menjadi `16px`. Kemudian elemen link pertama menggunakan tambahan class `btn-danger` yang akan mengubah warna latar belakang menjadi merah. Sedangkan elemen link kedua menggunakan tambahan class `btn-success` untuk mengubah warna latar belakang menjadi `green`.

---
<!-- *template: invert -->
## Nilai Properti CSS yang Umum

---

### Color

Semua warna pada CSS dibangun berdasarkan ruang warna sRGB (standard red, green, blue). Warna pada ruang ini adalah gabungan dari saluran warna merah, hijau dan biru.

Dengan menggabungkan level yang berbeda dari warna merah, hijau, dan biru, kita dapat menghasilkan jutaan warna.

---

#### Warna Kata Kunci

Nilai dari warna kata kunci adalah nama (seperti `red`, `green`, atau `blue`) yang memetakan ke warna yang diberikan. Sebagian besar warna memiliki nama kata kuncinya.

<style>
table {
	display: inline-block;
}
</style>

|Nama||
|:-|:-:|
|`black`|<span style="display: inline-block; width: 20px; height: 20px; background: black;"></span>|
|`silver`|<span style="display: inline-block; width: 20px; height: 20px; background: silver;"></span>|
|`gray`|<span style="display: inline-block; width: 20px; height: 20px; background: gray;"></span>|
|`white`|<span style="display: inline-block; width: 20px; height: 20px; background: white;"></span>|
|`maroon`|<span style="display: inline-block; width: 20px; height: 20px; background: maroon;"></span>|

|Nama||
|:-|:-:|
|`red`|<span style="display: inline-block; width: 20px; height: 20px; background: red;"></span>|
|`purple`|<span style="display: inline-block; width: 20px; height: 20px; background: purple;"></span>|
|`fuchsia`|<span style="display: inline-block; width: 20px; height: 20px; background: fuchsia;"></span>|
|`green`|<span style="display: inline-block; width: 20px; height: 20px; background: green;"></span>|
|`olive`|<span style="display: inline-block; width: 20px; height: 20px; background: olive;"></span>|

|Nama||
|:-|:-:|
|`lime`|<span style="display: inline-block; width: 20px; height: 20px; background: lime;"></span>|
|`yellow`|<span style="display: inline-block; width: 20px; height: 20px; background: yellow;"></span>|
|`navy`|<span style="display: inline-block; width: 20px; height: 20px; background: navy;"></span>|
|`blue`|<span style="display: inline-block; width: 20px; height: 20px; background: blue;"></span>|
|`teal`|<span style="display: inline-block; width: 20px; height: 20px; background: teal;"></span>|

---

**Contoh**: Mengganti warna latar belakang elemen dengan class `task` menjadi `maroon` dan elemen dengan class `count` menjadi `yellow`.
``` css
.task {
  background: maroon;
}

.count {
  background: yellow;
}
```

---

#### Warna Heksadesimal

Warna heksadesimal memuat tanda pagar `#`, diikuti oleh tiga atau enam angka atau huruf. Angkanya terdiri dari `0` sampai `9` dan hurufnya terdiri dari `a` sampai `f`. Nilai ini akan dipetakan ke saluran warna sRGB.

Pada notasi enam karakter, dua karakter pertama menyatakan saluran merah, karakter ketiga dan keempat menyatakan saluran hijau, dan dua karakter terakhir menyatakan saluran biru.

---

Jika masing-masing pasang karakter merupakan karakter yang sama, maka notasi 6 karakter dapat dipersingkat menjadi 3 karakter.  **Contoh**: `#ff6600` dapat dipersingkat menjadi `#f60`.

**Contoh**: Kita berikan warna `maroon` dan `yellow` seperti pada sebelumnya dengan menggunakan heksadesimal.
``` css
.task {
  background: #800000;
}

.count {
  background: #ff0;
}
```

---

#### Warna RGB dan RGBa

Nilai dair warna RGB adalah fungsi `rgb()` yang merupakan singkatan dari red, green, dan blue. Fungsi ini menerima 3 input, yaitu masing-masing bilangan bulat antara `0` sampai dengan `255`.

Inputan pertama dari fungsi `rgb()` untuk saluran merah, yang kedua untuk saluran hijau, dan yang ketiga untuk saluran biru.

---

**Contoh**: Kita berikan warna `maroon` dan `yellow` seperti pada sebelumnya dengan menggunakan warna RGB.
``` css
.task {
  background: rgb(128, 0, 0);
}

.count {
  background: rgb(255, 255, 0);
}
```

---

Nilai warna RGB juga dapat menyertakan saluran alfa atau transparansi dengan menggunakan fungsi `rgba()`. Fungsi `rgba()` memerlukan inputan keempat, yaitu bilangan real dari `0` sampai dengan `1`. Nilai ini menyatakan tingkat ketransparanan dari warna, `0` menyatakan tembus pandang sedangkan `1` menyatakan warna yang solid.

**Contoh**:
``` css
.task {
  background: rgba(128, 0, 0, .25);
}

.count {
  background: rgba(255, 255, 0, 1);
}
```

---

#### Warna HSL dan HSLa

Nilai warna HSL menggunakan fungsi `hsl()` yang menerima 3 inputan, yaitu hue, saturation dan lightness.

Hue merupakan bilangan tanpa unit dari `0` sampai `360`. Nilai `0` sampai `360` menyatakan roda warna, dan nilainya menyatakan derajat dari warna pada roda warna.

Nilai kedua dan ketiga, saturation dan lightness, merupakan persentase dari `0` sampai `100%`. Saturation menyatakan tingkat kecerahan warna, `0` berwarna abu-abu sedangkan `100%` berwarna cerah. 

---

Lightness menyatakan  seberapa terang warna kita, `0` menyatakan sangat gelap sedangkan `100%` menyatakan sangat terang.

**Contoh**: Kita berikan warna `maroon` dan `yellow` seperti pada sebelumnya dengan menggunakan warna HSL.
``` css
.task {
  background: hsl(0, 100%, 25%);
}

.count {
  background: hsl(60, 100%, 50%);
}
```

---

Seperti RGBa, nilai warna HSL juga memiliki  saluran alfa, atau transparansi, dengan menggunakan fungsi `hsl()`. Nilainya adalah bilangan real antara `0` dan `1`.

**Contoh**:
``` css
.task {
  background: hsla(0, 100%, 25%, .25);
}
.count {
  background: hsla(60, 100%, 50%, 1);
}
```

---

### Panjang

Nilai panjang pada CSS, serupa dengan warna, ada dua tipe yaitu panjang absolut dan panjang relatif, yang tujuan penggunanaannya juga berbeda.

---

#### Panjang Absolut

Panjang absolut merupakan panjang yang sudah pasti, seperti sentimeter, inci, dan lain-lain. Panjang absolut yang paling populer adalah pixel, dengan notasi `px`.

##### Pixel

Satu  pixel sama dengan 1/96 inci. **Contoh**: Mengubah ukuran paragraf menjadi 14 pixel.
``` css
p {
  font-size: 14px;
}
```

---

#### Panjang Relatif

Panjang relatif bergantung pada pengukuran panjang yang lain.

##### Persentase

**Contoh**: Kita ingin lebar dari suatu elemen setengah dari parentnya.
``` css
.col {
  width: 50%;
}
```

---

##### Em

Panjang em dihitung berdasarkan ukuran font dari elemen. Satu em sama dengan ukuran font dari elemen. **Contoh**: Jika ukuran font dari elemen adalah `14px` dan lebarnya adalah `5em` maka lebarnya adalah `70px` (14 dikali dengan 5).
``` css
.banner {
  font-size: 14px;
  width: 5em;
}
```

---

### Rangkuman

Hal yang sudah dipelajari:
* Bagaimana style mengalir dari atas ke bawah
* Apa itu spesifisiti dan cara menghitungnya
* Bagaimana cara menggabungkan selektor untuk memilih elemen yang spesifik
* Bagaimana menggunakan kelas majemuk pada satu elemen untuk memberikan style berlapis
* Nilai warna yang berbeda pada CSS, meliputi katakunci, heksadesimal, RGB, dan HSL

---

* Nilai panjang yang berbeda pada CSS, meliputi pixel, persentase, dan em
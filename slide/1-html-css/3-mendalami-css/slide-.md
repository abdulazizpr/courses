<!-- $theme: default -->

<link rel="stylesheet" type="text/css" href="C:\makersinstitute\slide\assets\style.css" />

<!-- MULAI SLIDE -->

<h1 class="section">HTML &amp; CSS &nbsp;&nbsp;</h1>

<div class="container-icon">
<img class="icon" src="http://images.all-free-download.com/images/graphiclarge/html_5_vector_logo_148263.jpg"><!--
--><img class="icon" src="http://jaspreetchahal.org/images/css3.svg">
</div>

<h2 class="section">Mengenal CSS</h2>

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Cascade</h1>

Semua style pada CSS tersusun dari atas ke bawah sehingga style dapat dimasukkan atau ditimpa dengan style yang baru.

**Contoh**:

``` css
p {
  background: orange;
  font-size: 24px;
}
p {
  background: green;
}
```
Semua background pada paragraf akan berwarna hijau karena pada selektor terakhir kita memberikan warna background menjadi hijau menimpa warna jingga yang didefinisikan sebelumnya. Sedangkan ukuran tulisannya akan tetap 24 pixel.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Cascade</h1>

## Cascading Properties

Cascade juga bekerja untuk properti di dalam selektor yang sama.

**Contoh**:
``` css
p {
  background: orange;
  background: green;
}
```
Karena deklarasi background hijau ditulis terakhir maka background dari paragraf akan berwarna hijau.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menghitung Specificity</h1>

Semua selektor mempunyai berat spesificity, yang akan menentukan urutan style.
Selektor tipe mempunyai berat specificity paling rendah, yaitu: `0-0-1`.
Selektor class mempunyai berat specificity yang sedang, yaitu: `0-1-0`.
Terakhir, selektor ID mempunyai berat specificity yang paling tinggi, yaitu: `1-0-0`.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menghitung Specificity</h1>

**HTML**:
``` html
<p id="food">...</p>
```

**CSS**:
``` css
#food {
  background: green;
}
p {
  background: orange;
}
```

Walaupun selektor ID ditulis lebih dulu dan selektor tipe ditulis terakhir, tetapi tetap background dari paragraf dengan `id` food akan berwarna hijau karena berat specificity dari selektor ID yang lebih tinggi.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menggabungkan Selektor</h1>

Dengan menggabungkan selektor kita dapat lebih spesifik memilih elemen atau grup elemen.

Sebagai contoh, kita ingin memilih semua elemen paragraf di dalam elemen yang nilai dari atribut class-nya adalah `hotdog` dan mengatur warna background-nya menjadi coklat atau `brown`. Tetapi ada satu paragraf yang nilai dari atribut class-nya adalah `mustard` yang ingin kita atur warna latar belakangnya menjadi kuning atau `yellow`.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menggabungkan Selektor</h1>

**HTML**:
``` html
<div class="hotdog">
  <p>...</p>
  <p>...</p>
  <p class="mustard">...</p>
</div>
```

**CSS**:
``` css
.hotdog p {
  background: brown;
}
.hotdog p.mustard {
  background: yellow;
}
```

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menggabungkan Selektor</h1>

Selektor yang digabung harus dibaca dari kanan ke kiri. Selektor yang dekat dengan tanda kurung kurawal merupakan *selektor kunci*. Selektor kunci akan elemen yang akan diberi style.

Gabungan selektor yang pertama yaitu, `.hotdog p`, memuat dua selektor: selektor class dan selektor tipe. Selektor kuncinya memilih elemen paragraf. Selektor ini akan memilih elemen paragraf yang berada di dalam class `hotdog`.

Yang kedua yaitu, `.hotdog p.mustard` memuat tiga selektor: dua selektor class dan satu selektor tipe. Perbedaannya hanya tambahan selektor class `.mustard` pada akhir dari selektor tipe paragraf. Maka `.mustard` akan menjadi selektor kunci.

<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">

---

<h1 class="judul">Menggabungkan Selektor</h1>



<img class="logo" src="C:\makersinstitute\slide\assets\makersinstitute-logo.png">
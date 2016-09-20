<!-- $theme: gaia -->
<!-- $size: 16:9 --->

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Box Model

---

# Outline:
* Menampilkan Elemen
* Box Model
* Developer Tools

---
<!-- *template: invert -->

## Menampilkan Elemen

---

### Display

Nilai yang umum untuk properti `display`:
* `block` Elemen blok mengambil tempat selebar parentnya. Elemen lain akan berada diatas atau dibawah elemen ini.
* `inline` Elemen inline memiliki lebar selebar kontennya. Tidak membuat baris baru.
* `inline-block` Elemen inline-blok memiliki sifat seperti elemen blok namun elemen ini berada pada baris yang sama, atau tidak pada baris baru. Tidak selalu menempel satu dengan yang lain.
* `none` Elemen none akan disembunyikan dan menganggap elemen tersebut tidak ada.

---

``` css
p {
   display: block;
}
```

``` css
p {
   display: inline;
}
```

``` css
p {
   display: inline-block;
}
```

``` css
div {
  display: none;
}
```

---
<!-- *template: invert -->

## Box Model

---

**Setiap elemen pada halaman merupakan box/kotak persegi panjang** yang memiliki lebar, tinggi, padding, border, dan margin.

![http://www.w3.org/TR/CSS2/images/boxdim.png](http://www.w3.org/TR/CSS2/images/boxdim.png)

---

Lebar total dari suatu elemen yaitu:

```
margin-right + border-right + padding-right + width + padding-left 
+ border-left + margin-left
```

Total tingginya yaitu:

```
margin-top + border-top + padding-top + height + padding-bottom 
+ border-bottom + margin-bottom
```

---

``` css
div {
  border: 6px solid #949599;
  height: 100px;
  margin: 20px;
  padding: 20px;
  width: 400px;
}
```

__Lebar Total:__ `492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px`

__Tinggi Total:__ `192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px`

---

### `width` &amp; `height`

#### `width`

Lebar default elemen level blok adalah `100%` mengisi parent.
Elemen level inline dan inline-blok akan memiliki lebar selebar kontennya. 
Elemen level inline tidak memiliki ukuran yang tetap, jadi properti `width` dan `height` hanya untuk elemen non-inline.

``` css
div {
  width: 400px;
}
```

---

#### `height`

Secara default, tinggi dari elemen tergantung dari kontennya.

``` css
div {
  height: 100px;
}
```

---

### `margin` & `padding`

#### `margin`

Properti `margin` menentukan ruang kosong disekitar elemen tersebut. Margin berada di luar border dan memiliki warna yang transparan. Margin dapat digunakan untuk menentukan posisi elemen pada halaman. Atau menentukan jarak ke elemen yang lainnya.

``` css
div {
  margin: 20px;
}
```

---

#### `padding`

Properti `padding` sangat mirip dengan properti `margin`; perbedaannya yaitu padding berada di dalam border elemen. 

``` css
div {
  padding: 20px;
}
```

---

###### `margin` &amp; `padding` pada Elemen Level Inline

Elemen level inline bekerja sedikit berbeda dengan elemen blok dan inline-blok untuk margin dan padding. Margin hanya bekerja secara horizontal&mdash;`left` dan `right`&mdash;pada elemen level inline. Padding bekerja untuk setiap sisi dari elemen level inline, tetapi `padding` secara vertikal&mdash;`top` dan `bottom`&mdash;akan menyatu dengan baris diatas dan dibawah dari elemen tersebut.

Margin dan padding bekerja secara normal untuk elemen blok dan inline-blok. 

---

#### Deklarasi Margin &amp; Padding

Versi pendek deklarasi properti `margin` dan `padding`.

``` css
div {
  margin: 20px; /* semua sisi */
}
```

``` css
div {
  margin: 10px 20px; /* top/bottom  left/right */
}
```

``` css
div {
  margin: 10px 20px 0 15px; /* top  right  bottom  left */
}
```


---

Versi panjang deklarasi properti `margin` dan `padding`.

``` css
div {
  margin-top: 10px;
  margin-right: 20px;
  margin-bottom: 0px;
  margin-left: 15px;
}
```
---

###### Warna Margin &amp; Padding

Properti `margin` dan `padding` benar-benar transparan dan tidak menerima nilai warna apapun. Walaupun transparan, mereka akan menampilkan warna latar belakang dari elemen yang terkait. Untuk margin, kita akan melihat warna latar dari elemen parent, dan untuk padding kita akan melihat warna latar untuk elemen tersebut.

---

### Border

Versi pendek:
``` css
div {
  border: 6px solid #949599;
}
```

Versi panjang:
``` css
div {
  border-width: 6px;
  border-style: solid; /*  solid, double, dashed, dotted, none. */
  border-color: #949599;
}
```

---

#### Sisi Border secara Individual

Hanya border bagian bawah:

``` css
div {
  border-bottom: 6px solid #949599;
}
```

Versi panjang:

``` css
div {
  border-bottom-width: 6px;
  border-bottom-style: solid;
  border-bottom-color: #949599;
}
```

---

#### Jari-Jari Border

Properti `border-radius` dapat membuat sudut dari elemen menjadi melengkung. Unit `border-radius` yaitu persentase dan pixel.

Versi Pendek:

``` css
div {
  border-radius: 5px; /* semua sudut */
}
```

``` css
div {
  border-radius: 5px 10px; /* top-left/bottom-right  top-right/bottom-left */
}
```

---

``` css
div {
  border-radius: 5px 10px 0 1px; /* top-left top-right 
                                     bottom-right bottom-left */
}
```

Versi Panjang:

``` css
div {
  border-top-left-radius: 5px;
  border-top-right-radius: 10px;
  border-bottom-right-radius: 0px;
  border-bottom-left-radius: 1px;
}
```

---

### Mengubah Ukuran Box

#### Nilai `content-box`

Nilai `content-box` merupakan nilai default.

``` css
div {
  -webkit-box-sizing: content-box;
     -moz-box-sizing: content-box;
          box-sizing: content-box;
}
```

**Lebar Total** = `margin-left` + `border-width` + `padding-left` + `width` + `padding-right` + `border-width` + `margin-right`

---

#### Nilai `padding-box`

Nilai `padding-box` mengikutsertakan nilai dari `padding` pada `width` dan `height` dari elemen tersebut. Untuk nilai `padding` yang semakin besar maka ukuran konten akan menyusut untuk menyesuaikan dengan lebarnya.

``` css
div {
  box-sizing: padding-box;
}
```

**Lebar Total** = `margin-left` + `border-width` + `width` + `border-width` + `margin-right`

---

#### Nilai `border-box`

Nilai `border-box` membuat nilai dari properti `border` dan `padding` termasuk dalam `width` dan `height` dari elemen tersebut. 

``` css
div {
  box-sizing: border-box;
}
```

**Lebar Total** = `margin-left` + `width` + `margin-right`

---

#### Memilih Box Size

Secara umum, nilai dari `box-sizing` yang terbaik adalah `border-box`, karena ukuran elemennya akan tetap untuk berapapun nilai `padding` dan `border`. Termasuk jika menetapkan `width` dengan menggunakan persentase, maka ukurannya akan tetap.

Kekurangannya hanya properti `box-sizing` belum didukung oleh semua browser, terutama untuk browser yang tua. Tetapi hal tersebut dapat teratasi dengan adanya update dari browser-browser tersebut.

---

## Developer Tools

![](http://learn.shayhowe.com/assets/images/courses/html-css/opening-the-box-model/developer-tools.png)

---

## Rangkuman

Hal yang sudah dipelajari:
* Tampilan dari elemen
* Apa itu box model dan mengapa penting
* Mengubah ukuran, termasuk tinggi dan lebar dari elemen
* Menambahkan margin, padding, dan border pada elemen
* Mengubah box sizing dari elemen dan efeknya pada box model

---

# Pertanyaan?

---

![Makers Institute](https://makersinstitute.id/img/logo-makersinstitute.png)

# Terima Kasih
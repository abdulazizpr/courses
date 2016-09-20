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
**Lebar:** `492px = 20px + 6px + 20px + 400px + 20px + 6px + 20px`
**Tinggi:** `192px = 20px + 6px + 20px + 100px + 20px + 6px + 20px`

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
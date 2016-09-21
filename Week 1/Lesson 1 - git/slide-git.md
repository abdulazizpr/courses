<h1 align = "center"> Introduction to Git </h1>
<br>
<br>

<img src="https://upload.wikimedia.org/wikipedia/commons/thumb/e/e0/Git-logo.svg/2000px-Git-logo.svg.png" align = "middle">


---
<h1 align = "center"> Git </h1>

## Definisi
Git adalah salah satu Version Control System (VCS), yaitu tools untuk code versioning dan manage project coding dari kecil sampai besar.

## Versioning?
* Tracking perubahan dari kode
* Mendokumentasikan perubahan-perubahan tersebut

---
# Ilustrasi Version Control
<img src="http://www.vogella.com/tutorials/Git/img/xvcs_state10.png.pagespeed.ic.mBoG0KsGsL.webp">

---
<h1 align = "center"> Jenis-Jenis Version Control System </h1>

* Localized VCS
Menyimpan local copies dari files.

* Centralized VCS
Menyediakan server untuk menyimpan semua files dan versionnya secara terpusat

* Distributed VCS
Semua user memiliki copy dari repository, dan merupakan full copy (clone) dari repository tersebut

---
## Ilustrasi Distributed VCS
<img src="http://www.vogella.com/tutorials/Git/img/xsharedrepo10.png.pagespeed.ic.C1ZPfVgen-.webp">

---
<h1 align = "center"> Repository Git </h1>

* Repository, atau biasa juga disebut "Project" berisi history dari kumpulan files dimulai dari direktori tertentu.
* Proses copy repository ke local folder --> cloning. Setelah cloning, maka user akan mendapatkan repository lengkap dengan history-nya.
* Jika kita clone repository, git akan secara default berasumsi bahwa kita akan bekerja pada repository ini.

---
<h1 align = "center"> Konsep Utama </h1>

Ada beberapa area, yaitu:
1. Workspace --> di mana user mengerjakan sesuatu (coding, dll)
2. Staging Area --> di mana user ingin menyimpan file yang ingin dimasukkan.
3. Repository --> di mana user menyimpan history dan branch (local)
4. Remote --> repository yang disimpan terpusat

---
# Git Interface

1. GUI
2. Command Line
---
<h1 align = "center"> Langkah-Langkah </h1>

1. Pastikan git sudah terinstall. Berikut <a href = "https://git-scm.com/book/en/v2/Getting-Started-Installing-Git"> tutorial install git. </a>

2. Inisiasi project atau repository dengan memasukkan command
``` html
git init
```
atau bisa juga dengan clone project git yang sudah ada, dengan command

``` html
git clone url-lokasi-project-berada
```
> Pastikan Anda berada di direktori yang tepat di mana Anda ingin mengerjakan project Anda
---
<h1 align = "center"> Langkah-Langkah </h1>

2. Buat atau edit sebuah code atau text file. Misalnya, file "hello.txt" yang berisi teks "Hello World!" di dalamnya.

3. Pindahkan ke staging area, dengan command:
```
git add nama-file
```
pada kasus ini, nama-file adalah "hello.txt"

> tips: pastikan selalu cek status repository, dengan command "git status"

---

<h1 align = "center"> Langkah-Langkah </h1>

4. Commit ke repository local, dengan command
```
git commit -m "custom message"
```

Pastikan "custom message" di atas diisi oleh message yang dimengerti oleh Anda dan tim project Anda, seperti:
1. "Menambahkan file normalize.css"
2. "Menambahkan tombol forgot password di file login.php"


---

<h1 align = "center"> Langkah-Langkah </h1>

5. Jika ingin menambahkan commit-an dan semua code ke remote repository, push semua commit-an dengan command:
```
git push origin nama_branch
```
Jika Anda tidak bisa push, berarti ada perubahan yang harus dicopy ke local repository kita terlebih dahulu. Maka, kita lakukan ini dengan command:
```
git pull lokasi_remote
```
atau, cara yang lebih aman

```
git fetch lokasi_remote
```

---
<h1 align = "center"> Pull vs Fetch </h1>

* Pull : menggabungkan (merging) semua perubahan (file juga commit) pada remote repository ke local repository

* Fetch : import hanya commitnya saja. Command ini berguna jika kita ingin me-review terlebih dahulu perubahan sebelum menggabungkan file ke local repository.

Pull juga bisa dilaksanakan dengan mengetikkan dua command berikut:

```
git fetch lokasi_remote
git merge nama_branch
```

---

<h1 align = "center"> Branching </h1>

* Bayangkan sebuah tim project yang besar (dari mulai developer hingga tester), ingin menambah banyak fitur baru untuk sebuah produk.

* Bagaimana tim tersebut bisa mengintegrasikan fitur-fitur baru tersebut sambil melakukan testing terhadap fitur baru tersebut tanpa membuat code berantakan?

* Jawaban: Branches, di mana tim bisa bekerja pada "direktori baru", yang nantinya bisa dihapus atau di merge.

---

<h1 align = "center"> Branching </h1>

* Bayangkan branch adalah folder-folder yang terpisah, yang masing-masing berisi file beserta history.

<img src ="http://i.stack.imgur.com/u8C1x.png">

---
<h1 align = "center"> Branching </h1>

* Command untuk menggabungkan file dan history antar branch

```
git merge nama_branch
```

---

<h1 align = "center"> Good Git Practice </h1>

1. Sering sering check in (add dan commit), terutama ketika code kita sudah bekerja atau memenuhi spek yang diberikan.

2. Tulis commit message dengan detail dengan kalimat yang bisa dimengerti oleh semua orang.

3. Untuk fitur-fitur baru, lakukan branching.
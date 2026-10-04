# Dokumen Teknis Modul 2 --- HTML Semantik, Tailwind CSS, dan Aksesibilitas

**Nama:** Bagas Efriliyanto Setiawan\
**NIM:** 105224049\
**Repositori:**
https://github.com/urbbaone/Praktikum-PAW-105224049-Bagas

## 1. Struktur Semantik

Pada Modul 2, halaman utama produk **Nusantara Coffee Export**
diperbaiki agar menggunakan struktur HTML semantik. Tujuannya adalah
supaya setiap bagian halaman mempunyai peran yang jelas dan dapat
dikenali oleh browser maupun teknologi bantu.

Struktur semantik yang diterapkan meliputi:

  -----------------------------------------------------------------------
  Elemen                              Fungsi pada halaman
  ----------------------------------- -----------------------------------
  `<header>`                          Bagian kepala halaman yang berisi
                                      identitas produk dan navigasi

  `<nav>`                             Kumpulan tautan navigasi menuju
                                      bagian halaman

  `<main>`                            Konten utama halaman produk

  `<section>`                         Mengelompokkan konten berdasarkan
                                      topik atau bagian

  `<aside>`                           Informasi tambahan yang berkaitan
                                      dengan konten utama

  `<footer>`                          Bagian penutup halaman
  -----------------------------------------------------------------------

Hierarki judul juga diperbaiki dengan menggunakan elemen heading sesuai
tingkatannya. Judul utama halaman menggunakan `<h1>`, kemudian
bagian-bagian berikutnya menggunakan heading yang sesuai.

Pada JSX, atribut HTML juga mengikuti aturan JSX, seperti `className`
sebagai pengganti `class` dan `htmlFor` sebagai pengganti `for`.

### 1.1 Produk yang Dikembangkan

Produk yang digunakan pada Modul 2 masih merupakan **Nusantara Coffee
Export** dari Modul 1. Halaman utama menampilkan informasi mengenai
kualitas dan proses ekspor kopi Indonesia.

Bagian yang terlihat pada halaman antara lain:

-   Navigasi Home, Quality Control, Our Coffees, dan Contact.
-   Hero section dengan judul **Export-Quality Coffee, Rigorous
    Standards**.
-   Informasi mengenai standar kualitas kopi.
-   Bagian proses quality control.
-   Informasi jenis dan klasifikasi kopi.
-   Bagian kontak dan footer.

### 1.2 Accessibility Tree

Pemeriksaan struktur semantik dilakukan melalui panel **Elements** pada
Chrome DevTools dan Accessibility Tree.

Pemeriksaan digunakan untuk melihat bagaimana browser mengenali struktur
halaman, termasuk landmark, heading, link, dan elemen interaktif.

![Accessibility Tree](../praktikum%202/Accessibility%20Tree.png)

**Gambar 1. Accessibility Tree halaman utama**

Dari pemeriksaan Accessibility Tree, elemen navigasi, heading, paragraf,
link, dan konten halaman dapat dikenali oleh browser. Pemeriksaan ini
digunakan sebagai pelengkap audit Lighthouse karena tidak semua masalah
aksesibilitas dapat ditemukan secara otomatis.

## 2. Tata Letak Responsif

Tata letak halaman menggunakan **Tailwind CSS** dengan pendekatan
**mobile-first**. Kelas tanpa awalan digunakan sebagai tampilan dasar
untuk layar kecil, kemudian breakpoint seperti `sm:` dan `lg:` digunakan
ketika layar menjadi lebih lebar.

Modul menetapkan tiga ukuran pengujian, yaitu **360 px, 768 px, dan 1280
px**. Indikator keberhasilannya adalah halaman tidak memiliki gulir
horizontal dan elemen tetap dapat digunakan pada ketiga ukuran tersebut.

### 2.1 Tampilan 360 px

Pada lebar 360 px, halaman menyesuaikan ukuran layar ponsel. Navigasi
dan konten disusun agar tetap dapat dibaca tanpa membuat halaman melebar
secara horizontal.

![Tampilan 360 px](../praktikum%202/Tampilan%20360%20px.png)

**Gambar 2. Tampilan halaman pada lebar 360 px**

### 2.2 Tampilan 768 px

Pada lebar 768 px, halaman mulai menggunakan ruang yang lebih luas.
Elemen yang sebelumnya bertumpuk dapat menggunakan susunan yang lebih
lebar sesuai breakpoint yang diterapkan.

![Tampilan 768 px](../praktikum%202/Tampilan%20768%20px.png)

**Gambar 3. Tampilan halaman pada lebar 768 px**

### 2.3 Tampilan 1280 px

Pada lebar 1280 px, halaman menggunakan ruang desktop yang lebih luas.
Navigasi dapat tersusun mendatar dan bagian konten dapat menggunakan
susunan beberapa kolom.

![Tampilan 1280 px](../praktikum%202/Tampilan%201280%20px.png)

**Gambar 4. Tampilan halaman pada lebar 1280 px**

### 2.4 Kelas Tailwind yang Digunakan

  --------------------------------------------------------------------------
  Kelas                      Fungsi                  Alasan Penggunaan
  -------------------------- ----------------------- -----------------------
  `flex`                     Mengaktifkan Flexbox    Menyusun elemen secara
                                                     fleksibel

  `flex-col`                 Mengatur Flexbox        Sesuai untuk tampilan
                             menjadi kolom           layar kecil

  `flex-row`                 Mengatur Flexbox        Digunakan pada layar
                             menjadi baris           yang lebih lebar

  `justify-between`          Membagi ruang pada      Membuat posisi elemen
                             sumbu utama             lebih rapi

  `items-center`             Meratakan elemen pada   Menjaga elemen tetap
                             sumbu silang            sejajar

  `gap-*`                    Memberikan jarak antar  Membuat jarak antar
                             elemen                  komponen konsisten

  `grid`                     Mengaktifkan CSS Grid   Menyusun konten dalam
                                                     baris dan kolom

  `grid-cols-1`              Membuat satu kolom      Sesuai untuk tampilan
                                                     mobile

  `sm:grid-cols-2`           Dua kolom mulai         Memanfaatkan ruang
                             breakpoint `sm`         layar yang lebih besar

  `lg:grid-cols-3`           Tiga kolom mulai        Sesuai untuk tampilan
                             breakpoint `lg`         desktop

  `lg:grid-cols-[2fr_1fr]`   Membuat dua kolom       Menempatkan konten
                             dengan perbandingan 2:1 utama lebih lebar
                                                     daripada informasi
                                                     tambahan

  `max-w-6xl`                Membatasi lebar         Mencegah konten terlalu
                             maksimum                melebar pada desktop

  `mx-auto`                  Margin otomatis         Membuat konten berada
                             kiri-kanan              di tengah

  `w-full`                   Menggunakan lebar penuh Membantu mencegah
                             yang tersedia           layout melebihi
                                                     viewport
  --------------------------------------------------------------------------

Pendekatan tersebut mengikuti prinsip mobile-first: tampilan dasar
dibuat untuk layar kecil terlebih dahulu, kemudian diperluas dengan
breakpoint untuk layar yang lebih besar.

## 3. Audit Aksesibilitas

Audit aksesibilitas dilakukan menggunakan **Lighthouse** pada Chrome
DevTools dengan kategori **Accessibility**.

Modul menetapkan target minimal **90** untuk halaman latihan setelah
perbaikan dan minimal **85** untuk halaman utama produk.

### 3.1 Hasil Lighthouse Sebelum dan Sesudah Perbaikan

  No.   Halaman               Kondisi               Skor Accessibility
  ----- --------------------- ------------------- --------------------
  1     `/latihan-audit`      Sebelum perbaikan                 **75**
  2     `/latihan-audit`      Sesudah perbaikan                 **95**
  3     `/` / halaman utama   Sesudah perbaikan                 **95**

### 3.2 Lighthouse Sebelum Perbaikan

Sebelum diperbaiki, halaman `/latihan-audit` memperoleh skor
Accessibility **75**.

![Lighthouse sebelum](../praktikum%202/Lighthouse%20sebelum.png)

**Gambar 5. Hasil Lighthouse halaman latihan sebelum perbaikan**

Beberapa audit yang gagal pada kondisi awal adalah:

  -----------------------------------------------------------------------
  Audit yang Gagal        Penyebab                Perbaikan
  ----------------------- ----------------------- -----------------------
  Buttons do not have an  Tombol hanya berisi     Menambahkan
  accessible name         ikon sehingga tidak     `aria-label` yang
                          mempunyai nama yang     sesuai dan membuat SVG
                          dapat dikenali          sebagai elemen
                          teknologi bantu         dekoratif dengan
                                                  `aria-hidden`

  Image elements do not   Elemen gambar tidak     Menambahkan `alt` yang
  have `[alt]` attributes memiliki teks           menjelaskan gambar atau
                          alternatif              `alt=""` jika dekoratif

  Form elements do not    Input belum mempunyai   Menambahkan
  have associated labels  label yang terhubung    `<label htmlFor>` yang
                                                  terlihat dan
                                                  menghubungkannya dengan
                                                  `id` input

  Background and          Kontras warna teks dan  Menggunakan warna teks
  foreground colors do    latar kurang            yang lebih gelap
  not have a sufficient                           sehingga kontras lebih
  contrast ratio                                  baik
  -----------------------------------------------------------------------

Selain temuan Lighthouse tersebut, pemeriksaan manual Accessibility Tree
menunjukkan bahwa judul yang ditulis menggunakan `<div>` sebaiknya
diganti menjadi `<h1>` agar struktur heading lebih bermakna.

### 3.3 Lighthouse Sesudah Perbaikan

Setelah perbaikan dilakukan, halaman `/latihan-audit` memperoleh skor
Accessibility **95**.

![Lighthouse sesudah](../praktikum%202/Lighthouse%20sesudah.png)

**Gambar 6. Hasil Lighthouse halaman latihan setelah perbaikan**

Skor **95** sudah memenuhi target minimal **90** untuk halaman latihan.

### 3.4 Lighthouse Halaman Utama

Audit juga dilakukan pada halaman utama produk setelah perbaikan. Hasil
audit yang diperoleh adalah **95**.

Pada audit halaman utama terdapat peringatan bahwa data tersimpan dapat
memengaruhi proses Lighthouse. Hal tersebut tidak mengubah skor
Accessibility yang diperoleh pada pengujian.

**Gambar 7. Hasil Lighthouse halaman utama**

> Screenshot hasil Lighthouse halaman utama menggunakan hasil pengujian
> langsung pada `http://localhost:3000`.

Skor **95** sudah memenuhi target minimal **85** untuk halaman utama.

### 3.5 Pemeriksaan Manual dengan Keyboard

Modul juga meminta pemeriksaan manual menggunakan tombol `Tab`, karena
beberapa masalah aksesibilitas seperti urutan fokus dan fokus yang
terlihat tidak selalu dapat ditemukan oleh audit otomatis.

Hal yang diperiksa:

  -----------------------------------------------------------------------
  Pemeriksaan                         Hasil
  ----------------------------------- -----------------------------------
  Elemen interaktif dapat menerima    Diperiksa menggunakan `Tab`
  fokus                               

  Urutan fokus mengikuti alur halaman Diperiksa secara manual

  Fokus terlihat secara visual        Diperiksa pada elemen yang sedang
                                      aktif

  Link dan tombol dapat dijangkau     Diperiksa menggunakan `Tab`

  Tidak ada fokus yang terjebak       Diperiksa dengan perpindahan fokus
  -----------------------------------------------------------------------

> Bukti screenshot khusus fokus keyboard belum tersimpan pada arsip yang
> digunakan untuk penyusunan dokumen ini. Jika pengujian dilakukan
> kembali, screenshot fokus tersebut dapat ditambahkan sebagai bukti
> tambahan.

## 4. Kendala dan Penyelesaian

### 4.1 Skor Lighthouse sebelum perbaikan masih 75

Kendala pertama adalah halaman latihan mendapatkan skor Accessibility
**75**. Beberapa masalah berasal dari tombol tanpa accessible name,
gambar tanpa `alt`, input tanpa label, dan kontras warna yang kurang.

**Penyelesaian:**\
Elemen gambar diberi `alt`, input diberi `<label>`, tombol ikon diberi
`aria-label`, SVG dekoratif diberi `aria-hidden`, dan warna teks
diperbaiki agar memiliki kontras yang lebih baik.

### 4.2 Lighthouse sempat gagal melakukan audit

Pada salah satu percobaan, Lighthouse menampilkan peringatan bahwa
halaman tidak melakukan paint dengan normal (`NO_FCP`). Lighthouse juga
memberikan peringatan bahwa data tersimpan dapat memengaruhi hasil.

**Penyelesaian:**\
Audit dijalankan kembali setelah halaman selesai dimuat. Browser dijaga
tetap berada di foreground selama proses audit. Sesuai petunjuk modul,
audit juga dapat dilakukan menggunakan jendela Incognito/InPrivate agar
pengaruh ekstensi dan data tersimpan dapat dikurangi.

### 4.3 Tampilan harus responsif pada tiga ukuran

Halaman harus berfungsi pada 360 px, 768 px, dan 1280 px tanpa gulir
horizontal.

**Penyelesaian:**\
Digunakan pendekatan mobile-first dengan Flexbox, Grid, `w-full`,
`max-w-*`, serta breakpoint seperti `sm:` dan `lg:`.

### 4.4 Perbaikan struktur semantik

Beberapa bagian halaman sebelumnya menggunakan elemen yang kurang
bermakna secara semantik.

**Penyelesaian:**\
Struktur halaman diperjelas menggunakan `<header>`, `<nav>`, `<main>`,
`<section>`, `<aside>`, dan `<footer>`. Judul utama juga menggunakan
`<h1>` dan heading berikutnya mengikuti hierarki yang sesuai.

## 5. Catatan Pemanfaatan AI

**Alat:** ChatGPT.

**Bagian yang digunakan:** bantuan memahami instruksi Modul 2,
menjelaskan struktur HTML semantik, penggunaan Flexbox dan Grid,
pendekatan mobile-first Tailwind CSS, analisis temuan Lighthouse,
penyusunan dokumen teknis Markdown, dan pengecekan urutan pengerjaan.

**Perintah utama yang digunakan dalam pengerjaan:**

``` text
Buat struktur dokumen teknis Week 2 berdasarkan Modul 2.
Jelaskan fungsi kelas Tailwind yang digunakan.
Bantu menganalisis hasil Lighthouse sebelum dan sesudah perbaikan.
Bantu menyusun dokumentasi dalam format Markdown seperti Modul 1.
```

**Cara verifikasi:** hasil bantuan AI tidak langsung dianggap sebagai
hasil pengujian. Implementasi diverifikasi melalui:

1.  halaman produk pada browser;
2.  Accessibility Tree pada Chrome DevTools;
3.  Lighthouse Accessibility;
4.  pengujian pada lebar 360 px, 768 px, dan 1280 px;
5.  pemeriksaan navigasi keyboard menggunakan tombol `Tab`;
6.  hasil skor Lighthouse yang ditampilkan langsung oleh browser.

Skor yang dicantumkan dalam dokumen merupakan hasil pengujian yang
diperoleh pada project.

## 6. Kesimpulan

Praktikum Modul 2 berhasil menerapkan struktur HTML semantik, tata letak
responsif menggunakan Tailwind CSS, dan perbaikan aksesibilitas pada
produk **Nusantara Coffee Export**.

Pada halaman latihan, skor Accessibility Lighthouse meningkat dari
**75** sebelum perbaikan menjadi **95** setelah perbaikan. Hasil
tersebut telah memenuhi target minimal 90 untuk halaman latihan.

Audit pada halaman utama juga memperoleh skor Accessibility **95**,
sehingga memenuhi target minimal 85 yang ditetapkan pada Modul 2.

Pengujian responsif dilakukan pada ukuran **360 px, 768 px, dan 1280
px**. Pemeriksaan Accessibility Tree digunakan untuk melihat struktur
semantik halaman, sedangkan pemeriksaan keyboard digunakan sebagai
pelengkap audit otomatis Lighthouse.

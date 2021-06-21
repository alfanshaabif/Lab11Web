# Praktikum 11
# Pemrograman Web
```
Alfansha Abiftyo Hadyatama
311910321
TI.19.A.2
```

## Persiapan
Sebelum memulai menggunakan Framework Codeigniter, perlu dilakukan konfigurasi pada webserver. 
Beberapa ekstensi PHP perlu diaktifkan untuk kebutuhan pengembangan Codeigniter 4.

Berikut beberapa ekstensi yang perlu diaktifkan:
- php-json ekstension untuk bekerja dengan JSON;
- php-mysqlnd native driver untuk MySQL;
- php-xml ekstension untuk bekerja dengan XML;
- php-intl ekstensi untuk membuat aplikasi multibahasa;
- libcurl (opsional), jika ingin pakai Curl

## LANGKAH 1
Untuk mengaktifkan ekstentsi tersebut, melalui XAMPP Control Panel, pada bagian Apache klik `Config` -> `PHP.ini`

<img width="616" alt="1" src="https://user-images.githubusercontent.com/56286071/122119272-2eefb180-ce53-11eb-969e-9ca89431f681.png">

Pada bagian `extention`, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. 
Kemudian simpan kembali filenya dan restart Apache web server.

<img width="637" alt="2" src="https://user-images.githubusercontent.com/56286071/122175025-7a36ae00-cead-11eb-93c0-d80144f2be02.png">



Kemudian buat folder baru dengan nama `lab11_php_ci` pada doc root webserver (`htdocs`)

<img width="591" alt="3" src="https://user-images.githubusercontent.com/56286071/122119465-6f4f2f80-ce53-11eb-8266-a4b0d8338b47.png">

## LANGKAH 2
## Instalasi Codeigniter 4
Untuk melakukan `instalasi Codeigniter 4` dapat dilakukan dengan dua cara, yaitu cara `manual` dan menggunakan `composer`. 
Pada praktikum ini kita menggunakan cara `manual`.

- Unduh Codeigniter dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

<img width="960" alt="4" src="https://user-images.githubusercontent.com/56286071/122119665-a7ef0900-ce53-11eb-9532-b6119c0e7695.png">

## LANGKAH 3
## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (`cd C:\xampp\htdocs\lab11_php_ci\ci4\`)
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah: `php spark`

<img width="677" alt="5" src="https://user-images.githubusercontent.com/56286071/122119777-c94ff500-ce53-11eb-9737-6f10451c8208.png">

## LANGKAH 4
## Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program. Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut.

<img width="960" alt="6" src="https://user-images.githubusercontent.com/56286071/122176757-2927b980-ceaf-11eb-940a-3fdeb7cadc3e.png">


Semua jenis error akan ditampilkan sama. Untuk memudahkan mengetahui jenis errornya, maka perlu mengaktifkan `mode debugging` dengan mengubah nilai konfigurasi pada environment variable `CI_ENVIRONMENT` menjadi `development`. Kemudian mengubah nama file `env` menjadi `.env` lalu setelah itu buka file tersebut dan ubah nilai variable `CI_ENVORNMENT` menjadi `development`. Setelah mengubah nilai konfigurasi pada environment variable `CI_ENVIRONMENT` menjadi `development`. maka hapus `tanda tagar (#)` pada awal baris `CI_ENVIRONMENT`. Dan yang terakhir, ubah kode pada file `app/Controller/Home.php` kemudian hilangkan `titik koma (;)` pada akhir kode seperti berikut.

<img width="960" alt="7" src="https://user-images.githubusercontent.com/56286071/122176796-30e75e00-ceaf-11eb-89cd-4039c9f90a56.png">


Maka hasilnya akan terjadi error seperti berikut.

<img width="960" alt="8" src="https://user-images.githubusercontent.com/56286071/122176855-4066a700-ceaf-11eb-8251-dc21cb31d8d2.png">

## LANGKAH 5
## Membuat Route Baru
Tambahkan kode berikut di dalam `app/config/Routes.php`

<img width="960" alt="9" src="https://user-images.githubusercontent.com/56286071/122180884-0a2b2680-ceb3-11eb-9654-159e4dcf492d.png">

Untuk mengetahui route yang ditambahkan sudah benar, buka CLI dan jalankan perintah berikut.
`php spark`

Ketik perintah berikut untuk menjalankan server CI 4 pada port 8080.
`php spark serve`

<img width="696" alt="10" src="https://user-images.githubusercontent.com/56286071/122183127-23cd6d80-ceb5-11eb-99db-bdd8d10ca238.png">

Selanjutnya coba `akses route` yang telah dibuat dengan mengakses alamat url http://localhost:8080/about seperti berikut. Maka hasilnya akan terjadi error, yang artinya file/page tersebut tidak ada. Untuk dapat mengakses halaman tersebut, harus dibuat terlebih dahulu `Controller` yang sesuai dengan routing yang dibuat yaitu `Controller Page`.

<img width="960" alt="11" src="https://user-images.githubusercontent.com/56286071/122186926-b9b6c780-ceb8-11eb-86dd-4ad6f445c69e.png">

## LANGKAH 6
## Membuat Controller
Selanjutnya adalah membuat `Controller Page`. Buat file baru dengan nama `page.php` pada direktori `Controller` kemudian isi kodenya seperti berikut.

<img width="960" alt="12" src="https://user-images.githubusercontent.com/56286071/122229253-c9e39c80-cee2-11eb-8217-ff07645b4390.png">

## LANGKAH 7
## Auto Routing
Secara default fitur autoroute pada `Codeiginiter` sudah aktif. Untuk mengubah status autoroute dapat mengubah nilai variabelnya. Untuk menonaktifkan ubah nilai `true` menjadi `false`. Kemudian tambahkan method baru pada `Controller Page` seperti berikut. Method ini belum ada pada `routing`, sehingga cara mengaksesnya dengan menggunakan alamat: http://localhost:8080/page/tos

<img width="960" alt="13" src="https://user-images.githubusercontent.com/56286071/122229400-e5e73e00-cee2-11eb-9990-b16a301d76e3.png">

## LANGKAH 8
### Membuat Views
Selanjutnya adalah membuat `view` untuk tampilan web agar lebih menarik. Buat file baru dengan nama `about.php` pada direktori `view (app/view/about.php)` kemudian isi kodenya seperti berikut. Kemudian ubah method `about` pada class `Controller Page` menjadi seperti berikut.

<img width="960" alt="14" src="https://user-images.githubusercontent.com/56286071/122229525-06af9380-cee3-11eb-9503-34c8ffbb0472.png">

Maka hasilnya seperti berikut

<img width="960" alt="15" src="https://user-images.githubusercontent.com/56286071/122229606-18913680-cee3-11eb-94f9-5bf4eb40b8d1.png">

## LANGKAH 9 
## Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan `css` dapat diimplementasikan dengan mudah pada `Codeigniter`. Yang perlu diketahui adalah pada `Codeigniter 4` file yang menyimpan asset `css` dan `javascript` terletak pada direktori public. Buat file `css` pada direktori public dengan nama `style.css` seperti berikut.

<img width="960" alt="16" src="https://user-images.githubusercontent.com/56286071/122229764-3a8ab900-cee3-11eb-9880-366130a99e6c.png">

Kemudian buat folder `template` pada direktori view kemudian buat file `header.php` dan `footer.php` seperti berikut.

<img width="960" alt="17" src="https://user-images.githubusercontent.com/56286071/122230038-76be1980-cee3-11eb-83ce-dfec25be0f77.png">

`File app/view/template/header.php`
`File app/view/template/footer.php`

<img width="960" alt="18" src="https://user-images.githubusercontent.com/56286071/122230146-93f2e800-cee3-11eb-9635-d923040db6aa.png">

Kemudian ubah file `app/view/about.php` seperti berikut.

<img width="960" alt="19" src="https://user-images.githubusercontent.com/56286071/122230195-9ce3b980-cee3-11eb-92e6-4b2166573f4f.png">

Hasilnya :

<img width="960" alt="20" src="https://user-images.githubusercontent.com/56286071/122230234-a5d48b00-cee3-11eb-8b59-a06710825865.png">


## Pertanyaan dan Tugas
Lengkapi kode program untuk menu lainnya yang ada pada Controller Page, sehingga semua link pada navigasi header dapat menampilkan tampilan dengan layout yang sama.

### Hasilnya :

<img width="960" alt="21" src="https://user-images.githubusercontent.com/56286071/122239224-f996a280-ceea-11eb-89b7-c4640af17258.png">

<img width="960" alt="22" src="https://user-images.githubusercontent.com/56286071/122239276-01564700-ceeb-11eb-9953-35578658d6c9.png">



# Praktikum 12 ( Lanjutan Codeigniter )
# Pemrograman Web

```
Alfansha Abiftyo Hadyatama
311910321
TI.19.A.2
```

## Persiapan
Pastikan `MySQL server` sudah berjalan, Kemudian buat sebuah `database` dan `table` sebagai berikut:

<img width="960" alt="1" src="https://user-images.githubusercontent.com/56286071/122739374-1c3f0780-d2ad-11eb-9ccd-13ab5ad83188.png">

<img width="960" alt="2" src="https://user-images.githubusercontent.com/56286071/122739404-23661580-d2ad-11eb-8333-e8f463388feb.png">

## LANGKAH 1
## Konfigurasi Koneksi Database
`Konfigurasi` dapat dilakukan dengan cara mengubah beberapa kode pada file `htdocs\lab11_php_ci\ci4\.env`.
Dan hilangkan tanda pagar `#` didepan. Maka jadi seperti dibawah ini.

<img width="960" alt="3" src="https://user-images.githubusercontent.com/56286071/122740254-fe25d700-d2ad-11eb-970c-e6f7502b3971.png">

## LANGKAH 2
## Membuat Model
Selanjutnya adalah `membuat Model` untuk memproses `data Artikel`. Buat file baru pada direktori `app/Models` dengan nama `ArtikelModel.php`

<img width="960" alt="4" src="https://user-images.githubusercontent.com/56286071/122740519-404f1880-d2ae-11eb-98fd-8bf9b7c5d396.png">

## LANGKAH 3
## Membuat Controller
Buat `Controller` baru dengan nama `Artikel.php` pada direktori `app/Controllers`.

<img width="960" alt="5" src="https://user-images.githubusercontent.com/56286071/122740666-65438b80-d2ae-11eb-84b4-b8d4ac6e99e6.png">

## LANGKAH 4
## Membuat View
Buat folder baru dengan nama `artikel` pada direktori `app/views`, kemudian buat file baru dengan nama `index.php`.

<img width="960" alt="6" src="https://user-images.githubusercontent.com/56286071/122740787-860be100-d2ae-11eb-8f10-08670c8480c3.png">

Selanjutnya buka browser kembali, dengan mengakses url http://localhost:8080/artikel

<img width="960" alt="7" src="https://user-images.githubusercontent.com/56286071/122740878-9c19a180-d2ae-11eb-9c90-71c18846983f.png">

Belum ada `data` yang diampilkan. Kemudian coba tambahkan beberapa `data` pada `database` agar dapat ditampilkan `datanya`.

<img width="960" alt="8" src="https://user-images.githubusercontent.com/56286071/122741356-12b69f00-d2af-11eb-8d29-4d7780d50a6e.png">

Refresh kembali browser, sehingga akan ditampilkan hasilnya.

<img width="960" alt="9" src="https://user-images.githubusercontent.com/56286071/122741688-6628ed00-d2af-11eb-8772-e15e1c6b020c.png">

## LANGKAH 5
## Membuat Tampilan Detail Artikel
Tampilan pada saat judul berita di klik maka akan diarahkan ke halaman yang berbeda. Tambahkan fungsi baru pada `Controller Artikel` dengan nama `view()`.

<img width="960" alt="10" src="https://user-images.githubusercontent.com/56286071/122741909-a1c3b700-d2af-11eb-855d-a3da359f077b.png">

## LANGKAH 6
## Membuat View Detail
Buat `view` baru untuk halaman detail dengan nama `app/views/artikel/detail.php`.

<img width="960" alt="11" src="https://user-images.githubusercontent.com/56286071/122742370-11d23d00-d2b0-11eb-8c13-b216e2c74f53.png">

## LANGKAH 7
## Membuat Routing Untuk Artikel Detail
Buka Kembali file `app/config/Routes.php`, kemudian tambahkan `routing` untuk `artikel detail`.

<img width="960" alt="12" src="https://user-images.githubusercontent.com/56286071/122742546-40e8ae80-d2b0-11eb-821c-2d6671caea15.png">

Maka akan tampil halaman dari artikel yang di klik.

<img width="960" alt="13" src="https://user-images.githubusercontent.com/56286071/122742664-61b10400-d2b0-11eb-92a1-9b658a0f8a7b.png">

## LANGKAH 8
## Membuat Menu Admin
Buat method baru pada `Controller Artikel` dengan nama `admin_index()`.

<img width="960" alt="14" src="https://user-images.githubusercontent.com/56286071/122742787-84dbb380-d2b0-11eb-9914-3b92ea338b46.png">

Kemudian buat `view` untuk tampilan `admin` dengan nama `admin_index.php`.

<img width="960" alt="15" src="https://user-images.githubusercontent.com/56286071/122742896-a046be80-d2b0-11eb-8791-68b7431d2f53.png">

Tambahkan `routing` untuk `menu admin` seperti berikut:

<img width="960" alt="16" src="https://user-images.githubusercontent.com/56286071/122742968-b785ac00-d2b0-11eb-8090-f5662bdc0e74.png">

Setelah itu buat `template header` dan `footer` baru untuk `Halaman Admin`. Buat file baru dengan nama `admin_header.php` pada direktori `app/view/template`

<img width="960" alt="17" src="https://user-images.githubusercontent.com/56286071/122743095-dd12b580-d2b0-11eb-9236-5cfb12f594b2.png">

Dan Buat file baru lagi dengan nama `admin_footer.php` pada direktori `app/view/template`

<img width="960" alt="18" src="https://user-images.githubusercontent.com/56286071/122743166-f3207600-d2b0-11eb-84ad-7833c841aa36.png">

Kemudian buat file baru lagi dengan nama `admin.css` pada direktori `ci4/public` untuk mempercantik tampilan `Halaman Admin`.

<img width="960" alt="19" src="https://user-images.githubusercontent.com/56286071/122743286-0fbcae00-d2b1-11eb-860e-5943f974277e.png">

<img width="960" alt="20" src="https://user-images.githubusercontent.com/56286071/122743332-1a774300-d2b1-11eb-9a88-1929e22a0404.png">

Akses `menu admin` dengan url http://localhost:8080/admin/artikel

<img width="960" alt="21" src="https://user-images.githubusercontent.com/56286071/122743434-2ebb4000-d2b1-11eb-828c-7e77d9d5b91e.png">

## LANGKAH 9
## Menambahkan Data Artikel
Tambahkan fungsi/method baru pada `Controller Artikel` dengan nama `add()`.

<img width="960" alt="22" src="https://user-images.githubusercontent.com/56286071/122744354-18fa4a80-d2b2-11eb-991a-2f38b205a0bb.png">

Kemudian buat `view` untuk `form tambah` dengan nama `form_add.php`

<img width="960" alt="23" src="https://user-images.githubusercontent.com/56286071/122744441-2d3e4780-d2b2-11eb-9071-87b85dde1546.png">

Klik menu `Tambah Artikel` dan inilah hasilnya.

<img width="960" alt="24" src="https://user-images.githubusercontent.com/56286071/122744515-3fb88100-d2b2-11eb-9341-a336a1593b9c.png">

## LANGKAH 10
## Mengubah Data
Tambahkan fungsi/method baru pada `Controller Artikel` dengan nama `edit()`.

<img width="960" alt="25" src="https://user-images.githubusercontent.com/56286071/122744627-5c54b900-d2b2-11eb-84a5-a00ed1a18741.png">

Kemudian buat `view` untuk `form tambah` dengan nama `form_edit.php`

<img width="960" alt="26" src="https://user-images.githubusercontent.com/56286071/122744743-7e4e3b80-d2b2-11eb-95cd-5de968758a82.png">

Klik ubah pada salah satu `artikel` dan inilah hasilnya :

<img width="960" alt="27" src="https://user-images.githubusercontent.com/56286071/122744820-96be5600-d2b2-11eb-9730-8c8c23f2e89b.png">

## LANGKAH 11
## Menghapus Data
Tambahkan fungsi/method baru pada `Controller Artikel` dengan nama `delete()`.

<img width="960" alt="28" src="https://user-images.githubusercontent.com/56286071/122744949-b5245180-d2b2-11eb-87cd-15e7fc6e407c.png">

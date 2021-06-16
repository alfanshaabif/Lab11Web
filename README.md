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

### Maka hasilnya seperti berikut

<img width="960" alt="15" src="https://user-images.githubusercontent.com/56286071/122229606-18913680-cee3-11eb-94f9-5bf4eb40b8d1.png">

## LANGKAH 9 
## Membuat Layout Web dengan CSS
Pada dasarnya layout web dengan `css` dapat diimplementasikan dengan mudah pada `Codeigniter`. Yang perlu diketahui adalah pada `Codeigniter 4` file yang menyimpan asset `css` dan `javascript` terletak pada direktori public. Buat file `css` pada direktori public dengan nama `style.css` seperti berikut.

<img width="960" alt="16" src="https://user-images.githubusercontent.com/56286071/122229764-3a8ab900-cee3-11eb-9880-366130a99e6c.png">

Kemudian buat folder `template` pada direktori view kemudian buat file `header.php` dan `footer.php` seperti berikut.

<img width="960" alt="17" src="https://user-images.githubusercontent.com/56286071/122230038-76be1980-cee3-11eb-83ce-dfec25be0f77.png">

### File app/view/template/header.php
### File app/view/template/footer.php

<img width="960" alt="18" src="https://user-images.githubusercontent.com/56286071/122230146-93f2e800-cee3-11eb-9635-d923040db6aa.png">

### Kemudian ubah file app/view/about.php seperti berikut.

<img width="960" alt="19" src="https://user-images.githubusercontent.com/56286071/122230195-9ce3b980-cee3-11eb-92e6-4b2166573f4f.png">

### Hasilnya :

<img width="960" alt="20" src="https://user-images.githubusercontent.com/56286071/122230234-a5d48b00-cee3-11eb-8b59-a06710825865.png">

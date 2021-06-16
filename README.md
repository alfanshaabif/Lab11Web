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


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

Untuk mengaktifkan ekstentsi tersebut, melalu XAMPP Control Panel, pada bagian Apache klik `Config` -> `PHP.ini`

<img width="616" alt="1" src="https://user-images.githubusercontent.com/56286071/122119272-2eefb180-ce53-11eb-969e-9ca89431f681.png">

Pada bagian extention, hilangkan tanda ; (titik koma) pada ekstensi yang akan diaktifkan. 
Kemudian simpan kembali filenya dan restart Apache web server.

<img width="459" alt="2" src="https://user-images.githubusercontent.com/56286071/122119362-49c22600-ce53-11eb-9bad-9229db75ecea.png">


## Kemudian buat folder baru dengan nama lab11_php_ci pada doc root webserver (htdocs)

<img width="591" alt="3" src="https://user-images.githubusercontent.com/56286071/122119465-6f4f2f80-ce53-11eb-8266-a4b0d8338b47.png">

## Instalasi Codeigniter 4
Untuk melakukan instalasi Codeigniter 4 dapat dilakukan dengan dua cara, yaitu cara manual dan menggunakan composer. 
Pada praktikum ini kita menggunakan cara manual.

- Unduh Codeigniter dari website https://codeigniter.com/download
- Extrak file zip Codeigniter ke direktori htdocs/lab11_ci.
- Ubah nama direktory framework-4.x.xx menjadi ci4.
- Buka browser dengan alamat http://localhost/lab11_ci/ci4/public/

<img width="960" alt="4" src="https://user-images.githubusercontent.com/56286071/122119665-a7ef0900-ce53-11eb-9532-b6119c0e7695.png">

## Menjalankan CLI (Command Line Interface)
Codeigniter 4 menyediakan CLI untuk mempermudah proses development. Untuk mengakses CLI buka terminal/command prompt.
Arahkan lokasi direktori sesuai dengan direktori kerja project dibuat (`cd C:\xampp\htdocs\lab11_php_ci\ci4\`)
Perintah yang dapat dijalankan untuk memanggil CLI Codeigniter adalah: `php spark`

<img width="677" alt="5" src="https://user-images.githubusercontent.com/56286071/122119777-c94ff500-ce53-11eb-9737-6f10451c8208.png">


## Mengaktifkan Mode Debugging
Codeigniter 4 menyediakan fitur debugging untuk memudahkan developer untuk mengetahui pesan error apabila terjadi kesalahan dalam membuat kode program.
Secara default fitur ini belum aktif. Ketika terjadi error pada aplikasi akan ditampilkan pesan kesalahan seperti berikut. Semua jenis error akan ditampilkan sama. 
Untuk memudahkan mengetahui jenis errornya, maka perlu diaktifkan mode debugging dengan Ubah nama file env menjadi .env kemudian buka file tersebut dan ubah nilai variable
CI_ENVIRINMENT menjadi development.

<img width="426" alt="6" src="https://user-images.githubusercontent.com/56286071/122120660-e507cb00-ce54-11eb-822d-fed132be9e67.png">

<img width="960" alt="7" src="https://user-images.githubusercontent.com/56286071/122120685-eafdac00-ce54-11eb-9911-4ea033a77658.png">



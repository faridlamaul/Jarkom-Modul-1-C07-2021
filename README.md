# Jarkom-Modul-1-C07-2021

## Soal 1

```
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
```
Filter yang digunakan : `http.host == "ichimarumaru.tech"`.

Web Server : nginx.

Cara mendapatkan :<br>
Setelah membuka kumpulan paket yang ada di dalam "1-5.pcap", pada isian kolom *display filter*, masukkan *syntax* yang diberikan.<br>
<img src="./assets/img/1.1.png"><br>
*Syntax* tersebut akan menghasilkan dua paket. Pilih salah satu paket. Kemudian ***follow TCP stream*** untuk melihat web server yang digunakan.<br>
<img src="./assets/img/1.2.png">

## Soal 2

```
Temukan paket dari web-web yang menggunakan basic authentication method!
```
Filter yang digunakan : `http.authbasic`.

Cara mendapatkan : <br>
Setelah membuka kumpulan paket yang ada di dalam "1-5.pcap", pada isian kolom *display filter*, masukkan *syntax* yang diberikan.<br>
<img src="./assets/img/2.1.png">



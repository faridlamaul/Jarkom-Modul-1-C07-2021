# Jarkom-Modul-1-C07-2021

## Soal 1

```
Sebutkan webserver yang digunakan pada "ichimarumaru.tech"!
```
Filter yang digunakan : `http.host == "ichimarumaru.tech"`.

Web Server : nginx.

Cara mendapatkan :<br>
Setelah membuka kumpulan paket yang ada di dalam "1-5.pcap", pada isian kolom *display filter*, masukkan *syntax* yang diberikan.<br>
<img src="./assets/img/1.1.png"><br><br>
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

## Soal 8

```
Cari paket yang menunjukan pengambilan file dari FTP tersebut!
```
Filter yang digunakan : `ftp.request.command == "RETR"`

Cara mendapatkan : <br>
Setelah membuka kumpulan paket yang ada di dalam "8-10.pcap", pada isian kolom *display filter*, masukkan *syntax* yang diberikan.<br>
<img src="./assets/img/8.1.png">

## Soal 9
```
Dari paket-paket yang menuju FTP terdapat indikasi penyimpanan beberapa file. Salah satunya adalah sebuah 
file berisi data rahasia dengan nama "secret.zip". Simpan dan buka file tersebut!
```
Filter yang digunakan : `ftp-data.command contains "secret.zip"`

Cara mendapatkan : <br>
Setelah membuka kumpulan paket yang ada di dalam "8-10.pcap", pada isian kolom *display filter*, masukkan *syntax* yang diberikan.<br>
<img src="./assets/img/9.1.png"><br><br>

*Syntax* tersebut akan menampilkan paket - paket pengiriman dari file "secret.zip". Pilih salah satu paket, kemudian ***follow TCP stream***.<br>
<img src="./assets/img/9.2.png"><br><br>

Setelah muncul tampilan menu ***follow TCP stream***, ubah kolom pengaturan *Show Data as* dari ASCII menjadi RAW. Kemudian, simpan filenya dengan mengklik tombol *Save AS*.<br>
<img src="./assets/img/9.3.png"><br><br>

Setelah file zip berhasil disimpan, buka file zip tersebut. Didalamnya akan terdapat file **wanted.pdf**.<br>
<img src="./assets/img/9.4.png"><br><br>

Ketika file tersebut akan dibuka, maka kita akan diminta untuk memasukkan passwordnya.<br>
<img src="./assets/img/9.5.png">

## Soal 10
```
Selain itu terdapat "history.txt" yang kemungkinan berisi history bash server tersebut! Gunakan isi dari "history.txt" untuk menemukan password untuk membuka file rahasia yang ada di "secret.zip"!
```
Filter yang digunakan : (1)`ftp-data.command contains "history.txt"` & (2)`ftp-data.command contains "bukanapaapa.txt"`.

Cara mendapatkan : <br>
Setelah membuka kumpulan paket yang ada di dalam "8-10.pcap", pada isian kolom *display filter*, masukkan *syntax* (1) yang diberikan.<br>
<img src="./assets/img/10.1.png"><br><br>

*Syntax* tersebut akan menampilkan paket pengiriman data dari file "history.txt". Klik paket tersebut, kemudian ***follow TCP stream***. Maka akan terlihat menu seperti berikut.<br>
<img src="./assets/img/10.2.png"><br><br>

Dari menu tersebut, terlihat sebuah perintah *bash* yang menunjukkan bahwa *key* dari file *secret.zip* berada di dalam file **bukanapaapa.txt**. Oleh karena itu, kita harus men-*trace* paket data pengiriman dari file  **bukanapaapa.txt** dengan memasukkan *syntax* (2) yang diberikan pada kolom display filter *wireshark*.<br>
<img src="./assets/img/10.3.png"><br><br>

Setelah mendapatkan paketnya, klik paket tersebut kemudian ***follow TCP stream***. Maka akan terlihat menu seperti berikut.<br>
<img src="./assets/img/10.4.png"><br><br>

Terlihat bahwa kita telah berhasil menemukan password untuk file *wanted.pdf* yaitu ***d1b1langbukanapaapajugagapercaya***. Ketikan password dimasukkan dan file dibuka, maka akan muncul poster *bounty* dari Monkey D. Luffy.<br>
<img src="./assets/img/10.5.PNG"><br><br>

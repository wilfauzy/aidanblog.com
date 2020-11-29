---
date: 2020-11-30 01:51:13 +0700
layout: post
title: Cara Menampilkan Tanggal dan Waktu
subtitle: Bagaimana Menampilkan Tanggal dan Waktu
description: Front matter jekyll biasanya tanggal post lalu judul postingan, setelah
  itu bisa diatur permalink sesuka kalian bisa dengan postname, atau beserta tanggal
  posting atau bisa juga dengan kombinasi path seperti post atau blog.
image: https://res.cloudinary.com/nadliw45/image/upload/v1606486226/pexels-bakr-magrabi-3203659_jwprol.jpg
optimized_image: https://res.cloudinary.com/nadliw45/image/upload/c_scale,w_380/v1606486226/pexels-bakr-magrabi-3203659_jwprol.jpg
category: jekyll
tags: blog
author: Wildan Fauzy
paginate: false

---
## Bagaimana Menampilkan Tanggal dan Waktu

Untuk menampilkan tanggal, ketik perintah:

```
date
```

Secara default hasilnya akan seperti ini:

```
Sen Nov 30 00:58:06 WIB 2020
```

Tampilkan tanggal menggunakan salah satu atau semua elemen berikut:

- **% a**: singkatan nama hari (mis. Sen, Sel, Rab)
- **% A** : nama hari penuh (mis. Senin, Selasa, Rabu)
- **% b** atau **% h** : singkatan nama bulan (mis. jan, feb, mar)
- **% B** : nama bulan penuh (Januari, Februari, Maret)
- **% c** : tanggal dan waktu lokal (tanggal dan waktu penuh)
- **% C** : abad - menampilkan yang *pertama* dua angka dari tahun (yaitu 19 untuk tahun 1999 dan 20 untuk tahun 2020)
- **% d** : hari dalam sebulan (yaitu 01, 02, 03)
- **% D** : sama dengan M / D / Y (yaitu 04/20/16)
- **% e** : hari dalam bulan diisi (yaitu '1', '2')
- **% F** : tanggal lengkap, sama seperti tttt-bb-hh
- **% H** : jam (00, 01, 02, 21, 22, 23)
- **% I** : jam (1,2,3,10,11,12)
- **% j** : hari dalam setahun (yaitu 243)
- **% k** : jam diisi (yaitu '1' menjadi '1')
- **% l** : jam empuk (format 12 jam)
- **% m** : nomor bulan (1,2,3)
- **% M** : menit (1,2,3,57,58,59)
- **% n** : baris baru
- **% N** : nanodetik
- **% p** : AM atau PM
- **% P** : suka% p tapi huruf kecil (ironisnya) 
- **% r** : lokal waktu 12 jam
- **% R** : versi 24 jam dari jam dan menit
- **% s** : detik sejak 1970-01-01 00:00:00
- **% S** : kedua (01,02,03, 57, 58, 59)
- **% t** : sebuah tab
- **% T** : waktu yang sama dengan% H:% M:% S
- **% u** : hari dalam seminggu (1 Senin, 2 Selasa, dll)
- **% U** : jumlah minggu tahun (dengan asumsi hari Minggu sebagai hari pertama dalam seminggu)
- **% V** : Nomor minggu ISO dengan Senin sebagai hari pertama minggu itu
- **% w** : hari dalam seminggu (0 adalah Minggu)
- **% W** : nomor minggu dalam setahun dengan Senin sebagai hari pertama minggu itu
- **% x** : representasi tanggal lokal (12/31/2015)
- **% X** : representasi waktu lokal (14:44:44)
- **% y** : dua digit terakhir tahun ini
- **% Y** : tahun
- **% z** : zona waktu numerik (yaitu -0400)
- **%: z** : zona waktu numerik sebagai berikut (yaitu -04: 00)
- **% :: z** : zona waktu numerik sebagai berikut (yaitu -04: 00: 00)
- **% Z** : singkatan zona waktu alfabetis (GMT) 
- **-** : satu tanda hubung mencegah padding nol
- **_** : satu bantalan garis bawah dengan spasi
- **0** : bantalan dengan angka nol
- **^** : gunakan huruf besar jika memungkinkan
- **#** : gunakan kasus sebaliknya jika memungkinkan

Untuk menampilkan hanya waktu gunakan yang berikut:

```
date +%T
```

Atau, gunakan yang berikut ini:

```
date +%H:%M:%S
```

Lampirkan juga tanggalnya dengan menggunakan perintah:

```
date +%d/%m/%Y%t%H:%M:%S
```

Atau, gunakan yang berikut (karena% T setara dengan% H:% M:% S):

```
date +$d/%m/%Y%t%T
```

Gunakan kombinasi apapun dari sakelar di atas setelah simbol plus untuk menampilkan tanggal sesuai keinginan Anda. Jika Anda ingin menambahkan spasi, Anda dapat menggunakan tanda kutip di sekitar tanggal.

```
date +'%d/%m/%Y %H:%M:%S'
```

## Menunjukkan Tanggal UTC

Lihat tanggal UTC untuk komputer Anda menggunakan perintah berikut:

```
date -u
```

Sebagai contoh menampilkan postingan tanggal otomatis dengan membuat initposth.sh, berikut:

```
POST_TITLE="${@:2:$(($#-1))}"
POST_NAME="$(echo ${@:2:$(($#-1))} | sed -e 's/ /-/g' | sed "y/ABCDEFGHIJKLMNOPQRSTUVWXYZ/abcdefghijklmnopqrstuvwxyz/")"
CURRENT_DATE="$(date -u +'%Y-%m-%d')"
TIME=$(date -u +"%T")
FILE_NAME="${CURRENT_DATE}-${POST_NAME}.md"
```

Front matter jekyll biasanya tanggal post lalu judul postingan, setelah itu bisa diatur permalink sesuka kalian bisa dengan postname, atau beserta tanggal posting.



*referensi: https://www.lifewire.com/display-date-time-using-linux-command-line-4032698*
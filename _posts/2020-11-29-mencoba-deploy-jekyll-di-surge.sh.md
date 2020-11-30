---
date: 2020-11-29T23:15:50.000+07:00
layout: post
title: "Mencoba Deploy Jekyll Di Surge.sh"
subtitle: Surge.sh deploy web static langsung dari terminal
description: bertemu salah satu layanan cdn untuk mendoploy static web yaitu surge.sh ternyata memang unik, di halaman website tidak ada user interface untuk login atau mendaftar ternyata semuanya dilakukan dengan command line
image: https://res.cloudinary.com/nadliw45/image/upload/c_scale,w_760/v1606486225/pexels-negative-space-34088_dv3i39.jpg
optimized_image: https://res.cloudinary.com/nadliw45/image/upload/c_scale,w_380/v1606486224/pexels-negative-space-169573_lyyqxo.jpg
category: jekyll
tags: surge.sh
author: Wildan Fauzy
paginate: false
---

Jika mendoploy website static biasanya menggunakan github repo lalu dideploy di berbagai layanan cdn seperti vercel atau netlify, jika menggunakan github page memang ada beberapa fitur yang dibatasi misalnya tidak bisa memasang plugin dalam directory _plugin akan ada peringatan keamanan.

Menjelajah di internet menemukan hal baru misalnya, bertemu salah satu layanan cdn untuk mendoploy static web yaitu surge.sh ternyata memang unik, di halaman website tidak ada user interface untuk login atau mendaftar ternyata semuanya dilakukan dengan command line di terminal.

Wah hal baru bagi saya, pasti bakal rumit nih kalo hubungannya sama command line terminal, dan memasukan baris perintah, ternyata setelah membaca bagian dokumentari di website surge.sh sepertinya mudah, tapi tidak tau dalam prakteknya akhirnya, langsung saja mencoba dari pada mati penasaran hehehe.

Pertama Install dulu surge.sh di komputer kalian dengan perintah berikut.

```
npm install --global surge
```

Sudah deh berhasil dipasang,  selanjutnya bingungkan sama saya juga wkwkkw.

Ternyata harus masuk dulu ke folder dimana projek static web kalian dibuat baru masukan perintah surge nanti akan menu login atau daftar di terminal, daftarnya cukup mudah, tinggal memasukan email dan password tidak perlu memasukan nama atau alamat.

Selanjutnya pastikan email yang kamu masukan aktif, lalu buka email untuk konfirmasi, sudah deh akun surge kalian berhasil dibuat, lalu masalahnya disini saya ingin mendeploy ssg Jekyll, disini saya menggunakan theme Jekflik yang membutuhkan Gulp jadi harus di deploy terlebih dahulu jekyllnya di komputer kalian sebelum diupload ke surge.

```
$ bundle exec jekyll build
$ gulp
```

Setelah berhasil di deploy secara lokal selanjutnya upload website jekyll ke surge dengan perintah berikut.

```
$ cd (folde projek website jekyll)
$ surge --domain https://aidanblog.com _site/
```

Sudah deh dalam beberapa detik blog jekyll kalian online, saat menulis ini saya menggunakan surge dan menulis lokal di komputer dengan aplikasi typora hehe.

Petuntuk lebih lanjut silakan baca docs di https://surge.sh
---
layout: post 
title: Membuat Lokal Web Server di Ubuntu dengan Apache2
date: 2018-12-3
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: apache.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [apache2, Linux]
---

Dalam artikel kita akan membahas tentang membuat lokal web server di ubuntu dengan apache2. Langsung saja..

### Langkah pertama
Langkah pertama adalah kita akan menginstall apache2 dengan command :

	sudo apt-get install apache2

### Langkah kedua
Langkah kedua adalah menginstall lynx. Command lynx ini berfungsi sebagai browser didalam terminal. Browser ini tetap tidak bisa menampilkan gambar karena berada didalam terminal, commandnya adalah :

	sudo apt-get install lynx

### Langkah ketiga
Langkah ketiga adalah kita akan mencoba membuka localhost dengan command lynx.

	lynx localhost

jika berhasil maka akan muncul seperti ini :

<img src="/assets/img/apache1.png">

Hal ini terjadi karena kita belum men-start apache2 tersebut, caranya dengan :

	systemctl start apache2

Setelah itu ketikkan command :

	systemctl status apache2

<img src="/assets/img/apache2.png">

### Langkah keempat
Langkah keempat adalah kita akan mencoba lagi membuka localhost dengan command lynx.

	lynx localhost

jika berhasil maka akan muncul seperti ini :

<img src="/assets/img/apache3.png">

Itulah pembahasan mengenai membuat lokal web server di ubuntu dengan apache2 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai membuat lokal web server di ubuntu dengan apache2 diatas mudah dipahami.
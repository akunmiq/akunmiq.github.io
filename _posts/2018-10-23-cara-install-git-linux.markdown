---
layout: post 
title: Cara Menginstall Git di Linux
date: 2018-10-23
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: git.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Git, Linux]
---

Kita sudah mengenal Git pada tulisan sebelumnya. Selanjutnya Kita akan melakukan instalasi dan persiapan untuk mulai belajar Git.

Mari kita mulai…

1.Cara Install Git di Linux

Instalasi Git pada Distro keluarga Debian dapat menggunakan perintah apt.

	sudo apt install git

atau

	sudo apt-get install git

Pada Fedora:

	yum install git

Setelah itu, coba perika versi yang terinstal dengan perintah:

	git --version

Pada komputer saya, versi yang terinstal adalah versi 2.7.4.

<img src="/assets/img/git-version.png">

2.Konfigurasi Awal yang Harus Dilakukan

Ada beberapa konfigurasi yang harus dupersiapakan sebelum mulai menggunakan Git, seperti name dan email.

Silahkan lakukan konfigurasi dengan perintah berikut ini.

	git config --global user.name "Petani Kode"
	git config --global user.email contoh@petanikode.com

Kemudian periksa konfigurasinya dengan perintah:

	git config --list

Apabila berhasil tampil seperti gambar berikut ini, berarti konfigurasi berhasil.

<img src="/assets/img/git-config.png">

Itulah pembahasan mengenai cara menginstall git di linux yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai cara menginstall git di linux diatas mudah dipahami.
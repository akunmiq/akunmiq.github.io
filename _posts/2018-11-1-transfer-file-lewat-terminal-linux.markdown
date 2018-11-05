---
layout: post 
title: Transfer File Lewat Terminal di Linux 
date: 2018-11-1
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: analyze.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [transfer, Linux]
---

Dalam artikel kita akan membahas tentang cara mentransfer file dengan mudah. Cara ini tidak memerlukan hardware, disini hanya memerlukan OS berbasis linux, terminal, dan SSH. Langsung saja..

#### Langkah pertama
Pastikan bahwa kita sudah menginstall ssh di Linux kita. Apabila belum silahkan install terlebih dahulu dengan cara:

	sudo apt-get install ssh

Maka ssh telah terinstall.

#### Langkah kedua
Kita membuat file dengan extensi '.tar.gz'.
CONTOH :
 Kita akan membuat file dengan nama contohdata.tar.gz dan akan ditaruh di /opt/myfolder.

	sudo tar cfvz contohdata.tar.gz /opt/myfolder

Lalu pastikan jika file tersebut owner nya adalah user kita bukan user root. Jika belum lakukan command:

	sudo chown -R miqdad:miqdad contohdata.tar.gz

#### Langkah ketiga
Setelah langkah-langkah sebelumnya selesai, sekarang kita akan mengirimkan file tersebut ketemen kita. Ada 2 cara untuk mengirim file tersebut:

##### Cara pertama
Cara ini digunakan jika kita ingin mengirim satu file saja. 

	scp * fesa@192.168.100.22:/opt/myfolder

##### Cara kedua
Cara ini digunakan jika kita ingin mengirim file lebih dari dua sekaligus.

	rsync * fesa@192.168.100.22:/opt/myfolder



Itulah pembahasan mengenai cara mentransfer file dengan mudah yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai cara mentransfer file dengan mudah diatas mudah dipahami.
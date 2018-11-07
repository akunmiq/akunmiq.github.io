---
layout: post 
title: Tutorial Create, Copy, Move, dan Delete File dan Directory
date: 2018-11-5
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: create.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [transfer, Linux]
---

Dalam artikel kita akan membahas tentang cara create, copy, move, and delete sebuah file dan directory. Langsung saja..

### 1. Create
Tutorial yang pertama adalah cara membuat file atau directory.

A. Cara untuk membuat sebuah file adalah dengan command 'touch'. CONTOH : 

	touch file.txt

dan cara untuk melihat file dan mengedit isi file tersebut dengan command,

	nano file.txt

untuk menyimpan file tersebut dengan cara tekan ctrl + x, lalu tekan Y.

B. Sedangkan cara untuk membuat sebuah directory (folder) adalah dengan command 'mkdir'. CONTOH :

	mkdir folder-baru

### 2. Copy
Tutorial yang kedua adalah cara untuk mengcopy sebuah file atau directory. Cara untuk mengcopy hal tersebut adalah dengan command 'cp'. CONTOH :

	cp file.txt latihan.txt

maksudnya adalah kita ingin mengcopy isi dari file.txt kedalam latihan.txt

### 3. Move
Tutorial yang ketiga adalah cara untuk memindahkan sebuah file atau directory ke tempat yang  ingin kita tuju. Cara untuk memindahkan hal tersebut adalah dengan command 'mv'. CONTOH :

	mv file.txt folder-baru

maksudnya adalah kita ingin memindahkan file.txt kedalam folder yang bernama folder-baru.

### 4. Delete
Tutorial yang keempat adalah cara untuk mendelete sebuah file atau directory. Cara untuk mendelete hal tersebut adalah dengan command 'rm -rf'. CONTOH :

	rm -rf file.txt folder-baru

maksudnya adalah kita ingin menghapus file.txt dan folder yang bernama folder-baru. 

Itulah pembahasan mengenai cara create, copy, move, and delete sebuah file dan directory yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai cara create, copy, move, and delete sebuah file dan directory diatas mudah dipahami.
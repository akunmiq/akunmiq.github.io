---
layout: post 
title: Compare and Manipulating File Content
date: 2018-10-29
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: manipulate.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Cat, Linux]
---

Dalam artikel kita akan membahas beberapa penggunaan command pada linux seperti 'cat', 'sort', 'pipe', less', dan 'more'. Langsung saja..

1.Command 'cat'

Fungsi dari command ini adalah untuk melihat isi dari sebuah file.

	cat test.txt

<img src="/assets/img/cat.png">

2.Command 'sort' 

Seperti artinya command sort memiliki fungsi untuk mengurutkan isi yang ada di dalam file. Secara default command sort akan mengurutkan sesuai abjad mulai dari A-Z. Jika ingin membalik dari Z-A maka tinggal menambahkan '-r' setelah kata 'sort'.

	sort test.txt

<img src="/assets/img/sort.png">

3.Command 'pipe'

 Fungsi dari command ini adalah untuk menyambungkan kedua command yang ingin kita jalankan sekaligus. Dan jika ingin keluar tekan saja huruf 'q'.

	sort test.txt | less

<img src="/assets/img/less.png">

4.Command 'less'

Fungsi dari command ini adalah untuk melihat isi file pada tiap barisnya. Ketika kita ingin mengganti baris sebelumnya atau selajutnya, kita bisa menggunakan tombol panah atas dan panah bawah yang ada di keyboard. Dan jika ingin keluar tekan huruf 'q'.

	sort test.txt | less

<img src="/assets/img/less.png">

5.Command 'more'

Fungsi dari command ini adalah untuk melihat isi file pada tiap barisnya. Ketika kita ingin mengganti baris sebelumnya atau selajutnya, kita bisa menggunakan tombol enter yang ada di keyboard.

	sort test.txt | more

<img src="/assets/img/more.png">

Itulah pembahasan mengenai Compare and Manipulating File Content yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai Compare and Manipulating File Content diatas mudah dipahami.
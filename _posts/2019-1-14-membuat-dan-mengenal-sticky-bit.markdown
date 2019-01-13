---
layout: post 
title: Membuat dan Mengenal Sticky Bit
date: 2019-1-14
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: stickybit.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [stickybit, Linux]
---

Dalam artikel kita akan membahas tentang membuat dan mengenal sticky bit. Sebelum masuk ke langkah-langkah bagaimana penggunaannya, mari kita ketahui terlebih dahulu apa itu sticky bit?

Sticky Bit adalah special permission yang mana hanya pada akun pemilik (user as owner) dan akun root yang bisa menghapus atau me-rename suatu direktori atau berkas. Artinya jika Anda login sebagai Fulan lalu men-sticky bit suatu berkas Anda, lalu ada orang lain ingin me-rename atau menghapusnya ia tidak akan bisa, meskipun kita mengeset permission-nya dengan 777 yang mana seharusnya semua user bisa saja menghapus atau rename direktori. Karena si Fulan men-sticky bit maka user lain yang satu group sekalipun tidak akan bisa. Perlu diketahui untuk menggunakan sticky bit, kita harus mengeset pada top directory / parent directory-nya.

Setelah mengetahui apa itu sticky bit, sekarang kita akan masuk ke langkah-langkah untuk membuat sticky bit.

###Langkah Pertama
Lankah pertama adalah kita ketahui dahulu dimana kita berada dengan command:

	whoami

<img src="/assets/img/sticky.png">

### Langkah Kedua
Langkah kedua adalah kita akan membuat sebuah folder terlebih dahulu. Disini kita akan membuat folder didalam /Documents, dengan command:

	sudo mkdir file-baru

<img src="/assets/img/sticky2.png">

### Langkah Ketiga
Langkah ketiga adalah kita akan merubah folder tersebut menjadi sticky bit, dengan command:

	sudo chmod 1777 file-baru

atau

	sudo chmod +t file-baru

<img src="/assets/img/sticky3.png">

Setelah folder kita buat sticky bit maka akan ada tambahan huruf 't' diakhir permission. 

### Langkah Keempat
Langkah keempat adalah kita akan ganti user dahulu dengan command:

	su saya

<img src="/assets/img/sticky4.png">	

### Langkah Kelima
Langkah kelima adalah kita akan masuk kedalam folder /Documents. Lalu kita coba hapus folder yang kita buat tadi, dengan command:

	sudo rm -rf file-baru

<img src="/assets/img/sticky5.png">

Disitu terlihat bahwa kita tidak dapat menghapus folder tersebut karena user 'saya' bukan owner dari folder tersebut. Jadi folder kita lebih aman dengan menngunakan sticky bit.

Itulah pembahasan mengenai membuat dan mengenal sticky bit yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai membuat dan mengenal sticky bit diatas mudah dipahami.
---
layout: post 
title: Cara Install OS di Virtual Box
date: 2018-12-22
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: virtualbox3.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [InstallOS, Linux]
---

Dalam artikel kita akan melanjutkan artikel sebelumnya tentang menginstall virtual box di linux ubuntu 16.04 dan sekarang kita akan membahas tentang cara install OS di virtual box. Langsung saja kita akan masuk ke langkah-langkah cara untuk install OS di virtual box.

### Langkah pertama
Langkah pertama adalah kita akan mendownload OS (.iso) terlebih dahulu.

Disini kita harus mendownload OS (.iso) yang kita butuhkan sebelum menginstallnya. Misal disini kita akan mencoba OS ubuntu 16.04.  

### Langkah kedua
Langkah kedua adalah kita akan membuat virtual machine baru.

A. Buka virtual dengan command :

	virtualbox

B. Klik tombol 'New'.

<img src="/assets/img/vbox1.png">

C. Set nama virtual machine sesuai keinginan kita dan ganti type OS menjadi linux. Lalu klik tombol 'next'.

<img src="/assets/img/vbox2.png">

D. Mengatur memory RAM untuk menjalankan Linux ubuntu tersebut. Dan untuk ukuran RAM-nya biarkan default (sesuai rekomendasi). Lalu klik tombol 'next'.

<img src="/assets/img/vbox3.png">

E. Pilih 'create a virtual hard disk now'. Lalu klik tombol 'create'.

<img src="/assets/img/vbox4.png">

F. Pilih 'VDI(VirtualBox Disk Image)' sebagai hard disk file type. Lalu klik tombol 'next'.

<img src="/assets/img/vbox5.png">

G. Lalu akan muncul 'Storage on physical hard disk', disini ada dua pilihan yang pertama 'Dynamically allocated' dan yang kedua 'Fixed size'. Untuk 'Dynamically allocated' dia akan membuat hard disk virtual yang misal besarnya 10 GB dan kita hanya menggunakan 3 GB dari 10 GB tersebut maka hard disk real pada komputer kita yang terpakai hanya 3 GB saja. Sedangkan untuk 'Fixed size' dia akan membuat hard disk virtual yang misal besarnya 10 GB dan kita hanya menggunakan 3 GB dari 10 GB tersebut maka hard disk real pada komputer kita yang terpakai akan 10 GB juga. Dan kami sarankan untuk memilih 'Dynamically allocated', lalu klik tombol 'next'.

<img src="/assets/img/vbox6.png">

H. Pilih lokasi penyimpanan hard disk dan nama nya. Untuk ukuran hard disk biarkan default (sesuai rekomendasi). Lalu klik tombol 'create'.

<img src="/assets/img/vbox7.png">

I. Jika muncul gambar seperti ini berarti anda telah berhasil membuat virtual hard disk baru. 

<img src="/assets/img/vbox8.png">

### Langkah Ketiga
Langkah ketiga adalah kita akan menambahkan OS (.iso).

A. Klik tombol 'Settings'

<img src="/assets/img/vbox8.png">

B. Klik tombol 'Storage'

<img src="/assets/img/vbox9.png">

C. Klik gambar CD pada pada bagian 'Controller:IDE'

<img src="/assets/img/vbox10.png">

D. Klik tombol 'Choose disk'

<img src="/assets/img/vbox11.png">

E. Klik file ISO ubuntu, dan ini kita harus tau dimana tempat kita menyimpan download-an OS (.iso) tersebut. Lalu klik 'open'.

<img src="/assets/img/vbox12.png">

F. Klik tombol start untuk memulai virtual machine yang kita buat barusan

<img src="/assets/img/vbox13.png">

Dan jika muncul gambar dibawah ini maka sudah berhasil.

<img src="/assets/img/vbox14.png">

Itulah pembahasan mengenai cara install OS di virtual box yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai cara install OS di virtual box diatas mudah dipahami.
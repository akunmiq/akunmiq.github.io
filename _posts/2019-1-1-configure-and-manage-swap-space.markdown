---
layout: post 
title: Configure and Manage Swap Space
date: 2019-1-1
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: swap4.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [swap, Linux]
---

Dalam artikel kita akan membahas tentang configure and manage swap space. Sebelum masuk ke langkah-langkah bagaimana penggunaannya, mari kita ketahui terlebih dahulu apa itu configure and manage swap space?

Swap adalah ruang pada Hardisk yang dijadikan ruang Virtual Memori (memory bayangan), yang digunakan ketika komputer membutuhkan lebih banyak memory dan space.

Swap berfungsi sebagai memori tambahan untuk memori fisik (RAM) dikomputer kita. Di semua system operasi (termasuk Linux) memori mempunyai fungsi sebagai tempat untuk penyimpanan sementara berbagai macam modul dan driver-driver yang dibutuhkan untuk menjalankan suatu system operasi, yang sekaligus juga digunaka untuk menjalankan aplikasi-aplikasi yang kita jalankan, kekurangan dari memori fisik adalah kapasitasnya yang relatif kecil, sehingga terkadang system terasa lambat dikarenakan penggunaan memori fisik di system telah penuh terpakai, untuk mengatasi hal tersebut maka digunakanlah suatu metode yang dikenal dengan Virtual Memori, di sistem Linux memori bayangan ini biasanya merupakan suatu partisi di hardisk yang mempunyai tipe file sistem Linux Swap, akan tetapi sebenarnya di Linux kita bisa membuat ataupun menambahkan Virtual Memori tanpa mengubah partisi di hardisk yaitu dengan menggunakan file yang mempunyai ekstensi (jenis file) misalnya contoh.swp yang akan kita gunakan sebagai Virtual Memory.

Setelah mengetahui apa itu configure and manage swap space, sekarang kita akan masuk ke langkah-langkah untuk penggunaan configure and manage swap space.

## Bagian pertama tentang SWAP Partisi

### Langkah pertama
Langkah pertama adalah kita ingin menggunakan partisi untuk dijadikan swap, pasti yang kita butuhkan pertama kali adalah partisinya. Disini kita mempunyai sdb1 ukuran 1GB yang akan kita jadikan sebagai swap area, dan di situ kita sudah mempunyai swap asli yaitu 1GB.

<img src="/assets/img/swap.png">

Setelah menentukan partisi mana yang akan kita gunakan, kita jalankan command:

	mkswap /dev/sdb1

### Langkah kedua
Langkah kedua adalah kita akan mengaktifkan swap, dengan command:

	swapon /dev/sdb1

lalu akan terlihat berbeda dari sebelumnya.

<img src="/assets/img/swap2.png">

### Langkah ketiga
Langkah ketiga adalah kita akan mengecek hard disk dan RAM space, dengan command: 

	free -mt

### Langkah keempat
Langkah keempat adalah kita akan mempermanenkan partisi swap kita agar tidak ke-reset saat kita matikan komputer, pertama kita masuk ke:

	nano /etc/fstab

Lalu masukkan '/dev/sdb1 swap swap defaults 0 0' dibaris paling bawah.

<img src="/assets/img/swap3.png">	

## Bagian kedua tentang SWAP file

### Langkah pertama
Langkah pertama adalah kita akan membuat Swapfile, dengan command:

	dd if=/dev/zero of=/root/myswapfile bs=1M count=1024

### Langkah kedua
Langkah kedua adalah kita akan kita ganti permission nya, dengan command:

	chmod 600 /root/myswapfile

Lalu jalankan command ini untuk menjadikan swap

	mkswap /root/myswapfile

### Langkah ketiga
Langkah ketiga adalah kita akan mengaktifkan swap, dengan command:

	swapon /root/myswapfile

### Langkah keempat
Langkah keempat adalah kita akan mempermanenkan partisi swap kita agar tidak ke-reset saat kita matikan komputer, pertama kita masuk ke:

	nano /etc/fstab

Lalu masukkan '/root/myswapfile swap swap defaults 0 0' dibari paling bawah.

<img src="/assets/img/swap3.png">

### Langkah kelima
Langkah kelima adalah kita akan kita akan mengecek hard disk dan RAM space, dengan command: 

	free -mt

Itulah pembahasan mengenai configure and manage swap space yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai configure and manage swap space diatas mudah dipahami.
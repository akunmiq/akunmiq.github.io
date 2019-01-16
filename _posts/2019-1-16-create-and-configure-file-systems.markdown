---
layout: post 
title: Create and Configure File Systems
date: 2019-1-16
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: btrfs2.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [filesystem, Linux]
---

Dalam artikel kita akan membahas tentang create and configure file systems.

Untuk mengorganisasi file-file pada device diperlukan suatu metode yang disebut dengan filesystem. Jika Anda mengenal FAT selama ini di sistem operasi Windows maka Anda akan mengenal beberapa metode filesystem di Linux, seperti ext fs, ext2 fs atau xia fs dll. Saat ini ext4 adalah filesystem yang banyak digunakan untuk Linux karena terkenal sangat efisien. Meskipun demikian Red Hat Linux tetap menyediakan dukungan terhadap filesystem lain seperti msdos yang sudah built in di kernel atau dalam bentuk modul seperti vfat (Windows95 native fs), ext,umsdos dan sebagainya.

Sekarang kita akan masuk ke langkah-langkah untuk penggunaan create and configure file systems.

### Langkah pertama
Langkah pertama adalah kita ingin membuat sebuah partisi terlebih dahulu. Disini kita mempunyai partisi dari 'sdb'.

<img src="/assets/img/filesys.png">

### Langkah kedua
Langkah kedua adalah kita akan membuat folder baru, dengan command:

	cd /mnt

	sudo mkdir ext4

	sudo mkdir btrfs

### Langkah ketiga
Langkah ketiga adalah kita akan mengubah file system 'sdb1', dengan command: 

	sudo mkfs -t ext4 /dev/sdb1

### Langkah keempat
Langkah keempat adalah kita akan mengubah file system 'sdb2', dengan command:

	sudo mkfs -t btrfs /dev/sdb2

Jika kalian mengalami error seperti gambar berikut, maka anda belum mendownload btrfs.

<img src="/assets/img/btrfs.png">

lalu kita download terlebih dahulu btrfs dengan command:

	sudo apt-get update

	sudo apt-get install btrfs-tools

lalu kita jalankan lagi command:

	sudo mkfs -t btrfs /dev/sdb2

### Langkah kelima
Langkah kelima adalah kita akan mengemount 'sdb1' ke /mnt/ext4, dengan command:

	sudo mount /dev/sdb1 /mnt/ext4

### Langkah keenam
Langkah kenam adalah kita akan kita mengemount 'sdb2' ke /mnt/btrfs, dengan command:

	sudo mount /dev/sdb2 /mnt/btrfs

### Langkah ketujuh
Langkah ketujuh adalah kita akan mengecek apakah dah berhasil apa belum, dengan command:

	lsblk

Jika output yang keluar seperti gambar berikut berarti kita telah berhasil

<img src="/assets/img/filesys2.png">

Itulah pembahasan mengenai configure and manage swap space yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai configure and manage swap space diatas mudah dipahami.
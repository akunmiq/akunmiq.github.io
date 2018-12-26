---
layout: post 
title: Konfigurasi Sistem Agar Mount Secara Otomatis
date: 2018-12-26
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: mount-back.jpeg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [mount, Linux]
---

Dalam artikel kita akan membahas tentang konfigurasi sistem agar mount secara otomatis. Perlu diketahui, didalam linux tidak semua device langsung ter-mount oleh system secara otomatis setelah kita menyalakan komputer kita. Ada beberapa yang harus kita mount secara manual agar bisa kita gunakan. Berbeda dengan Windows, yang semua sudah serba nge-mount secara otomatis sehingga kita tinggal pakai saja.

Sekarang kita akan coba konfigurasi sistem agar melakukan mount secara otomatis terhadap partisi kita, agar setiap kita menyalakan atau me-reboot komputer kita partisi kita bisa langsung di pakai. 

Langsung saja kita akan masuk ke langkah-langkah untuk konfigurasi sistem agar mount secara otomatis.

### Langkah pertama
Langkah pertama adalah kita cek dahulu hard disk kita, dengan command:

	lsblk

<img src="/assets/img/mount1.png">

### Langkah kedua
Langkah kedua adalah akan mengubah File System 'sdb1' menjadi ext4 dengan command:

	mkfs -t ext4 /dev/sdb1

<img src="/assets/img/mount2.png">

### Langkah ketiga
Langkah ketiga adalah lakukan beberapa command dibawah ini. 

	cd /mnt

	ls -la

	mkdir mountbaru

<img src="/assets/img/mount3.png">

### Langkah keempat
Langkah keempat adalah kita akan mount 'sdb1' ke mountbaru, dengan command:

	mount /dev/sdb1 /mnt/mountbaru

lalu ketikkan command:

	lsblk

<img src="/assets/img/mount4.png">

Di sini kita mempunyai sebuah partisi yaitu sdb1 yang kita mount ke /mnt/mountbaru.

### Langkah kelima
Langkah kelima adalah kita akan melihat UUID, type file system, dan lain2 dari semua device milik kita, dengan command:

	blkid

<img src="/assets/img/mount5.png">

Lalu kita copy UUID dari 'sdb1' yaitu /dev/sdb1: UUID="f6b152ec-3f95-45a1-811e-4180b17c58d8"

### Langkah keenam
Langkah kenam adalah setelah kita tadi meng-copy UUID dari 'sdb1', sekarang kita akan masuk ke /etc/fstab, dengan commmand:

	nano /etc/fstab

<img src="/assets/img/mount6.png">

lalu paste UUID dibaris paling bawah, seperti ini

<img src="/assets/img/mount7.png">

- UUID="f6b152ec-3f95-45a1-811e-4180b17c58d8" : UUID milik 'sdb1' yang telah dicopy.

- /mnt/mountbaru : Tempat dimana 'sdb1' kita mount.

- ext4 : Type file system dari 'sdb1'.

- Angka 0 : Sudah aturan dari sananya begitu.

- Angka 2 : Nomer untuk menandakan kapan parisi tersebut diproses, tinggal lanjutin nomer yang sudah ada.

Lalu kita simpan dengan menekan 'ctrl + x' lalu tekan 'Y' dan terakhir 'enter'.

### Langkah ketujuh
Langkah ketujuh adalah kita akan mereboot virtual box kita, dengan command:

	reboot

Jika telah selesai reboot nya lalu kita ketikkan command:

	lsblk

<img src="/assets/img/mount8.png">

Jika outputnya seperti gambar diatas berarti kita telah berhasil.

Itulah pembahasan mengenai konfigurasi sistem agar mount secara otomatis yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai konfigurasi sistem agar mount secara otomatis diatas mudah dipahami.
---
layout: post 
title: Membuat dan Mengelola RAID.
date: 2019-1-7
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: raid.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [RAID, Linux]
---

Dalam artikel kita akan membahas tentang membuat dan mengelola RAID. Diartikel sebelumnya kita sudah mengenal apa itu RAID dan beberapa tingkatannya. Sekarang kita akan membahas bagaimana cara membuat RAID tersebut. Langsung saja kita akan masuk ke langkah-langkah untuk membuat dan mengelola RAID.

### Langkah Pertama
Langkah pertama adalah kita akan mendownload 'mdadm' terlebih dahulu dengan command:

	sudo apt-get install mdadm

### Langkah Kedua
Langkah kedua adalah kita akan membuat partisi yang bertipe 'Linux RAID'

<img src="/assets/img/raid-1.png">

### Langkah Ketiga
Langkah ketiga adalah kita akan membuat RAID dengan command:

	sudo mdadm --create --verbose /dev/md0 --level=stripe --raid-devices=2 /dev/sdb1 /dev/sdb2

### Langkah Keempat
Langkah keempat adalah kita akan mengecek RAID dengan command:

	cat /proc/mdstat

<img src="/assets/img/raid-2.png">

Lalu jalankan command ini:

	sudo mdadm --detail /dev/md0

<img src="/assets/img/raid-3.png">

### Langkah Kelima
Langkah kelima adalah kita akan mengubah file system dengan command:

	sudo mkfs -t ext4 /dev/md0

### Langkah Keenam
Langkah keenam adalah kita akan memount RAID dengan command:

	sudo mount /dev/md0 /mnt

lalu kita akan cek kembali dengan command:

	df -h

### Langkah Ketujuh
Langkah ketujuh adalah kita akan menampilkan UUID RAID dengan command:

	sudo mdadm --detail --scan

### Langkah Kedelapan
Langkah kedelapan adalah kita akan menambahkan UUID ke dalam file 'mdadm.conf' dengan commannd:

	sudo nano /etc/mdadm/mdadm.conf

Copy semua yang kalian dapat dari perintah sebelum ini lalu letakkan paling bawah dan save.

### Langkah Kesembilan
Langkah kesembilan adalah kita akan menambahkan assemble :

	sudo mdadm --assemble --scan

### Langkah Kesepuluh
Langkah kesepuluh adalah kita akan mengupdate mdadm :

	sudo update-rc.d mdadm defaults

### Langkah Kesebelas
Langkah kesepuluh adalah kita akan mengaktifkan devices :

	sudo nano /etc/default/mdadm

lalu tambahkan 'AUTOSTART=true' pada kolom paling akhir lalu save.

Itulah pembahasan mengenai membuat dan mengelola RAID yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai membuat dan mengelola RAID diatas mudah dipahami.
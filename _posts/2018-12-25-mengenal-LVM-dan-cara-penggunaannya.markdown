---
layout: post 
title: Mengenal LVM (Logical Volume Manager) dan Cara Penggunaannya
date: 2018-12-11
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: lvm-back.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [LVM, Linux]
---

Dalam artikel kita akan membahas tentang mengenal LVM (Logical Volume Manager) dan cara penggunaannya. Sebelum masuk ke langkah-langkah bagaimana menggunakannya, mari kita ketahui terlebih dahulu apa itu LVM (Logical Volume Manager)?

LVM adalah sebuah manajemen penyimpan di sistem operasi GNU/Linux yang menyediakan fleksibilitas dalam membuat dan mengubah partisi dalam sebuah disk. LVM menambahkan lapisan antara antarmuka I/O kernel dengan perangkat fisik untuk mendapatkan logical-view dari penyimpan. Dengan adanya lapisan inilah kita dapat melakukan perubahan partisi baik itu resize, penghapusan, dan lain - lain secara live pada sistem baik untuk satu atau lebih media. 
Kemudahan tersebut akan membuat administrator maupun pengguna lebih nyaman dalam melakukan manajemen dan alokasi ruang penyimpan hingga penamaan volume. Selain itu kita dapat melakukan snapshot dan membuat block-device salinan sebuah partisi atau lebih untuk mencatat statusnya dengan tujuan backup

Beberapa istilah yang dikenal di dunia LVM yaitu :

A. Physical Volume (PV)
adalah physical disk atau media penyimpan secara fisik baik itu berupa partisi secara konvensional misal: hda1, hda3, hdc5,sda3 maupun RAID..

B. Volume Group (VG)
adalah sebuah volume yang dibuat dari satu atau lebih PV dalam media penyimpan dan juga sebagai manajer bagi PV dan LV.

C. Logical Volume (LV)
adalah partisi secara logical yang dibuat di atas VG dan pada LV inilah filesystem akan diletakkan.

D. Physical Extents (PE)
adalah bagian-bagian atau potongan yang membentuk sebuah PV, dengan PE ini dapat ditentukan maksimal ukuransebuah VG.

E. Logical Extents (LE)
adalah bagian atau potongan yang membentuk LV,ukurannya sama dengan PE.

Setelah mengetahui apa itu LVM (Logical Volume Manager), sekarang kita akan masuk ke langkah-langkah untuk menggunakan LVM.

### Langkah pertama
Langkah pertama adalah kita akan menginstall LVM (Logical Volume Manager), dengan command:

	sudo apt-get install lvm2

### Langkah kedua
Langkah kedua adalah Kita cek dahulu hard disk kita, dengan command:

	lsblk

<img src="/assets/img/lvm2.png">

Disini kita harus mempunyai 2 partisi terlebih dahulu, dan dari gambar diatas bisa kita lihat ada sdb1 dan sdb2. Untuk yang belum tau cara buat partisi bisa lihat link disini: https://miqdadhome.com/membuat-partisi-harddisk-dilinux-ubuntu-16.04/

### Langkah ketiga
Langkah ketiga adalah kita harus merubah type partisi menjadi 'Linux LVM'. Type partisi itu sangatlah banyak dan kita bisa melihat listnya dengan mengetikan huruf 'l'. Dan untuk 'Linux LVM' berada di nomer 30. 

<img src="/assets/img/lvm3.png">

Untuk cara merubah type partisi bisa mengetikkan huruf 't'.

<img src="/assets/img/lvm4.png">

Jika sudah selesai ketikkan huruf 'w' untuk menyimpannya.

### Langkah keempat
Langkah keempat adalah kita akan mebuat Physical Volume, langkah ini akan mendefinisikan partisi mana yang akan kita pakai untuk Logical Volume nantinya. Caranya dengan ketikkan command:

	pvcreate /dev/sdb1 /dev/sdb2

<img src="/assets/img/lvm5.png">

### Langkah kelima
Langkah kelima adalah kita akan membuat Volume Group, caranya dengan ketikkan command:

	vgcreate datagabungan /dev/sdb1 /dev/sdb2

Kata 'datagabungan' itu cuma nama, bisa diisi sesuai keinginan kita.

<img src="/assets/img/lvm6.png">

### Langkah keenam
Langkah keenam adalah kita akan membuat Logical Volume, caranya dengan ketikkan command:

	lvcreate --name logical-data --size 490M datagabungan
 
- logical-data : nama untuk Logical Volume, bisa diisi sesuai keinginan kita.
     
- 490M : ukuran untuk gabungan partisi kita.
     
- datagabungan: nama pada saat kita membuat Volume Group, nama ini harus sama. 

<img src="/assets/img/lvm7.png">

Lalu coba kita cek dengan command:

	lvdisplay

<img src="/assets/img/lvm8.png">

### Langkah ketujuh
Langkah ketujuh adalah kita akan mengubah File System Logical Volume tadi menjadi ext4 dengan command:

	mkfs -t ext4 /dev/datagabungan/logical-data

<img src="/assets/img/lvm9.png">

### Langkah kedelapan
Langkah kedelapan adalah lakukan beberapa command dibawah ini.

	cd /mnt

	ls -la

	mkdir datakecil

<img src="/assets/img/lvm10.png">

### Langkah kesembilan
Langkah kesembilan adalah kita akan mount Logical Volume yang kita buat tadi ke datakecil.

	mount /dev/datagabungan/logical-data /mnt/datakecil

Lalu ketikkan command:

	df -h

<img src="/assets/img/lvm11.png">

### Langkah kesepuluh
Langkah kesepuluh adalah kita akan menambahkan partisi baru ke Logical Volume yang barusan kita buat, agar Logical Volume kita punya size yang lebih besar. Caranya adalah sebagai berikut:

A. Buat partisi baru sisa ukuran dari sdb. Caranya seperti kita membuat partisi pada biasanya.

<img src="/assets/img/lvm12.png">

B. Rubah type partisi dengan command 't'.

<img src="/assets/img/lvm13.png">

Lalu ketikkan command 'w' untuk menyimpan, dan disitu muncul perintah untuk mereboot virtualboxnya.

C. Setelah direboot, lalu kita cek kembali dengan command:

	lsblk

<img src="/assets/img/lvm14.png">

### Langkah kesebelas
Langkah kesebelas adalah kita akan mebuat Physical Volume dari sdb3, dengan command:

	pvcreate /dev/sdb3 

lalu kita cek dengan command:

	pvs

<img src="/assets/img/lvm15.png">

### Langkah kedua belas
Langkah kedua belas adalah kita akan mengextend Volume Group. Disini kita akan menambahkan sdb3 kedalam file datagabungan, dengan command:

	vgextend datagabungan /dev/sdb3

lalu kita cek dengan command:

	vgs

<img src="/assets/img/lvm16.png">

lalu ketikkan command:

	vgdisplay

### Langkah ketiga belas
Langkah ketiga belas adalah kita akan mengextend Logical Volume, dengan command:

	lvextend -l +130 /dev/datagabungan/logical-data

Angka '+130' ini adalah jumlah Free PE, jumlah ini bisa kita lihat dengan mengetikkan command 'vgdisplay'. Jadi jumlah ini disesuaikan dengan milik masing2.

<img src="/assets/img/lvm17.png">

lalu ketikkan command:

	e2fsck -f /dev/datagabungan/logical-data

<img src="/assets/img/lvm18.png">

lalu ketikkan command:

	resize2fs /dev/datagabungan/logical-data

<img src="/assets/img/lvm19.png">

### Langkah keempat belas
Langkah keempat belas adalah kita akan mengemount, dengan command:

	mount /dev/datagabungan/logical-data /mnt/datakecil

lalu ketikkan command:

	df -h

<img src="/assets/img/lvm20.png">

Jika berhasil maka akan terlihat ukuran sizenya akan bertambah.

Itulah pembahasan mengenai mengenal LVM (Logical Volume Manager) dan cara penggunaannya yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai mengenal LVM (Logical Volume Manager) dan cara penggunaannya diatas mudah dipahami.
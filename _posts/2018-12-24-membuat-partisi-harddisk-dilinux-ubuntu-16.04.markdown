---
layout: post 
title: Membuat Partisi Hard Disk di Linux Ubuntu 16.04
date: 2018-12-24
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: partisi2.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [partisi, Linux]
---

Dalam artikel kita akan membahas tentang membuat partisi hard disk di linux ubuntu 16.04. Karena ini berhubungan dengan hard disk, maka akan lebih baik jika kita menggunakan virtual box agar lebih aman. Untuk yang belum tau tentang virtual box bisa dilihat disini: https://miqdadhome.com/install-virtualbox-dilinux-ubuntu-16.04/

Anda tentu tidak asing dengan istilah partisi maupun tabel partisi. Dua entitas inilah yang mendefinisikan ‘ruangan’ pada hard disk. Bagi Anda yang tergolong pengguna PC awam atau tidak terlalu paham mengenai partisi, suatu hard disk dapat dianalogikan seperti sebidang tanah kosong. Sebelum dapat dipakai, tanah tersebut harus dibagi dalam petak-petak kecil terlebih dahulu. Petak inilah yang diibaratkan seperti partisi. Adapun tabel partisi diandaikan papan keterangan di depan area tanah yang menjelaskan berapa petak yang di dalam area tanah dan berapa luas masing-masing petak. Di dalam petak ini nantinya “ditanami” data, yang dalam wujudnya sehari-hari dapat dilihat sebagai file.

Sebelum dapat ditanami, petak-petak tersebut harus diolah terlebih dahulu. Proses pengolahan inilah yang dikenal sebagai proses format hard disk. Saat melakukan format, Anda dapat memilih berbagai format sistem file (file system). Apabila di Windows, tersedia format FAT atau NTFS. Di Linux, dikenal beberapa sistem file, diantaranya yang cukup populer adalah sistem file ext2,ext3 dan ext4.

Sebelum mulai, kita setting virtual box kita agar bisa kita remote dari terminal laptop kita, ini akan lebih memudahkan kita daripada harus mengopersikan langsung di dalam virtual box.

### Langkah pertama
Langkah pertama adalah kita akan mensetting virtual box agar bisa diremote dari terminal kita.

A. Klik 'setting' lalu klik 'Network'

<img src="/assets/img/part1.png"> 

B. Dibagian 'Attached to' rubah menjadi 'Bridged Adapter'. Lalu klik 'OK'

<img src="/assets/img/part2.png"> 

### Langkah kedua
Langkah kedua adalah kita akan menginstall openssh server.

Untuk caranya bisa dilihat disini: https://sites.google.com/a/student.unsika.ac.id/anggayudap/linux/tutorial-install-dan-konfigurasi-ssh-pada-ubuntu-server

### Langkah ketiga
Langkah ketiga adalah kita akan membuat hard disk virtual baru.

A. Klik 'setting' lalu klik 'storage'. Lalu dibagian 'Controller:SATA' klik icon 'add hard disk' (paling kanan) dan pastikan terlebih dahulu bahwa virtual machine dalam keadaan power off. Lalu klik 'Create new disk'.

<img src="/assets/img/part3.png">

B. Pilih 'VDI(VirtualBox Disk Image)' sebagai hard disk file type. Lalu klik tombol 'next'.

<img src="/assets/img/part4.png">

C. Pilih 'Dynamically allocated'. Lalu klik tombol 'next'.

<img src="/assets/img/part5.png">

D. Pilih lokasi penyimpanan hard disk dan nama nya. Untuk ukuran hard disk kita buat 1 GB saja. Lalu klik tombol 'create'.

<img src="/assets/img/part6.png">

E. Setelah membuat hard disk baru, kita bisa start virtual machine nya agar bisa kita remote.

### Langkah keempat
Langkah keempat adalah kita remote virtual machine kita lalu kita masuk kelangkah-langkah untuk membuat partisi hard disk.

A. Kita cek dahulu hard disk kita, dengan command:

	lsblk

<img src="/assets/img/part7.png">

B. Kita masuk ke fdisk dengan command

	sudo fdisk /dev/sdb

output nya akan seperti ini:

<img src="/assets/img/part8.png">

untuk melihat panduan bisa ketik m lalu enter, di situ akan keluar pilihan2 yang bisa kita gunakan.

C. Kita akan membagi 'sdb' menjadi beberapa bagian 

<img src="/assets/img/part9.png">

Dari gambar diatas akan kami jelaskan bagian-bagiannya sebagai berikut:

	Command (m for help): n { n = membuat pastisi baru}

	Partition type

		p   primary (0 primary, 0 extended, 4 free)
		e   extended (container for logical partitions)

	Select (default p): p 	{ kita pilih primary }

	Partition number (1-4, default 1):  { plih default saja=langsung tekan enter}

	First sector (2048-2116509, default 2048):  { pilih default }

	Last sector, +sectors or +size{K,M,G,T,P} (2048-2116509, default 2116509): +200M  { ukuran partisi yang kita inginkan}

	Created a new partition 1 of type 'Linux' and of size 200 MiB.

	Command (m for help): 

D. Kita akan mengecek apakah sudah berhasil atau belum, dengan command 'p'(print):

Sebelum dibuat partisi

<img src="/assets/img/part10.png">

Setelah dibuat partisi

<img src="/assets/img/part11.png">

Jika kita ingin menyimpan partisi tersebut bisa tulis command 'w' lalu enter. Dan jika ingin keluar bisa tulis command 'quit'.

E.Kita cek lagi hard disk kita, dengan command:

	lsblk

<img src="/assets/img/part12.png">

Disitu terlihat dibagian 'sdb' ada 'sdb1' itu berarti partisi kita tadi telah berhasil. Dan jika anda ingin membuat partisi lagi silahkan lakukan hal yang sama seperti diatas.	

Itulah pembahasan mengenai membuat partisi hard disk di linux ubuntu 16.04 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai membuat partisi hard disk di linux ubuntu 16.04 diatas mudah dipahami.
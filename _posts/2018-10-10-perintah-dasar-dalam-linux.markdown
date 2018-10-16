---
layout: post 
title: Perintah Dasar dalam LINUX
date: 2018-10-10
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: terminal.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Perintahdasar, Linux]
---

Linux merupakan software sistem operasi open source yang gratis untuk disebarluaskan di bawah lisensi GNU. Sistem operasi Linux yang dikenal dengan istilah distribusi Linux (Linux distribution) atau distro Linux umumnya sudah termasuk perangkat-perangkat lunak pendukung seperti server web, bahasa pemrograman, basisdata, tampilan desktop (desktop environment) seperti GNOME,KDE dan Xfce juga memiliki paket aplikasi perkantoran (office suite) seperti Open Office.org, KOffice,Abiword.

Setelah kita mengetahui sejarah dan penegrtian lInux, kali ini kita akan memepelajari perintah-perintah dasar Linux. Karena untuk melakukan eksekusi pada aplikasi Linux banyak menggunakan perintah-perintah dasar. Berikut beberapa perintah-perintah dasar yang terdapat pada Linux.

1. sudo su
   
   Berfungsi untuk melakukan login sebagai root/pengguna tertinggi
   
   sintaks: sudo su

2. cd (change directory)
   
   Berfungsi untuk berpindah directory/folder
   
   sintaks: cd alamat_directory
   
   contoh: cd /etc/network

3. pwd
   
   Berfungsi untuk memperlihatkan direktori mana posisi kita berada
   
   sintaks : pwd

4. ls(list)
   
   Berfungsi untuk melihat isi sebuah direktori
   
   sintaks: ls

5. mv(move)
   
   Berfungsi untuk memindahkan,cut atau rename file
   
   sintaks: mv /directory/nama_file_asal /nama_file_baru

6. mkdir(make direktori)
   
   Berfungsi untuk membuat folder baru
   
   sintaks: mkdir nama_folder
   
   contoh: mkdir folder1

7. touch
   
   Berfungsi untuk membuat file baru
   
   sintaks: touch nama_file

8. rm(remove)
   
   Berfungsi untuk menghapus file
   
   sintaks: rm file1.txt

9. echo
   
   Berfungsi untuk menuliskan sesuatu kata atau kalimat ke sebuah file
   
   sintaks: echo “isi pesan” nama_file

10. dmesg
   
    Berfungsi untuk melihat hardware yang sedang beraktifitas
   
    sintaks: dmesg

11. top
   
    Berfungsi untuk melihat proses yg sedang berjalan seperti task manager di windows
   
    sintaks: top

12. cpuinfo
   
    Berfungsi untuk melihat spesifikasi computer
   
    sintaks: cpuinfo

13. meminfo
   
    Berfungsi untuk melihat status RAM
   
    sintaks: more /proc/meminfo

14. clear
   
    Berfungsi untuk membersihkan layar
   
    sintaks: clear

15. exit
   
    Berfungsi untuk keluar dari terminal
   
    sintaks: exit

16. wget
   
    Berfungsi untuk mendownload via terminal
   
    sintaks : wget link_download

17. ifconfig
   
    Berfungsi untuk melihat konfigurasi Ethernet/kartu jaringan
   
    sintaks : ifconfig

18. apt-get
   
    Berfungsi untuk memperoleh paket/software dari repository ubuntu secara online
   
    sintaks: apt-get nama_paket
   
    contoh: apt-get install dhcp3-server

19. who
   
    Berfungsi untuk melihat nama login kita
   
    sintaks: who

20. cat
   
    Berfungsi untuk membuka file
   
    sintaks : cat nama_file

21. hostname
   
    Berfungsi untuk menampilkan nama computer
   
    sintaks: hostname

22. free
   
    Berfungsi untuk free memori
   
    sintaks : free

23. history
   
    Berfungsi untuk melihat perintah apa saja yg pernah di ketik
   
    sintaks: history

Itulah pembahasan mengenai perintah dasar dalam linux yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai perintah dasar dalam linux diatas mudah dipahami.
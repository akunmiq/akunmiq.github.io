---
layout: post 
title: Pengertia dan Pentingnya Git bagi Programmer
date: 2018-10-15
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: git.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Git, Linux]
---

Git adalah salah satu tool yang sering digunakan dalam proyek pengembangan software.

Git bahkan menjadi tool yang wajib dipahami oleh programmer, karena banyak digunakan di mana-mana.

Pada kesempatan ini kita akan belajar Git dari dasar.

Artikel ini hanya akan membahas pengenalan Git saja. Untuk mempelajari Git lebih lanjut, saya sudah menyediakan link di bagian akhir.

Mengenal Git
Git adalah salah satu sistem pengontrol versi (Version Control System) pada proyek perangkat lunak yang diciptakan oleh Linus Torvalds.

Pengontrol versi bertugas mencatat setiap perubahan pada file proyek yang dikerjakan oleh banyak orang maupun sendiri.

Git dikenal juga dengan distributed revision control (VCS terdistribusi), artinya penyimpanan database Git tidak hanya berada dalam satu tempat saja.

<img src="https://d33wubrfki0l68.cloudfront.net/5d30666dda588f5e24d11ad4ba9bc2b9e5202cf8/cc89a/img/git/sistem-git.png" alt="Sistem VSC Terdistribusi">

Semua orang yang terlibat dalam pengkodean proyek akan menyimpan database Git, sehingga akan memudahkan dalam mengelola proyek baik online maupun offline.

Dalam Git terdapat merge untuk menyebut aktifitas penggabungan kode.

Sedangkan pada VCS (Version Control System) yang terpusat… database disimpan dalam satu tempat dan setiap perubahan disimpan ke sana.

<img src="https://d33wubrfki0l68.cloudfront.net/d5ab9318ff5d6d86a678aec96465e30d5d051ac5/d06f9/img/git/vcs-terpusat.png" alt="Sistem VCS Terpusat">

VCS terpusat memiliki beberapa kekurangan:

Semua tim harus terkoneksi ke jaringan untuk mengakses source-code;
Tersimpan di satu tempat, nanti kalau server bermasalah bagaimana?
Karena itu, Git hadir untuk menutupi kerkurangan yang dimiliki oleh VCS terpusat.

Apa yang dilakukan oleh Git?
Git sebenarnya akan memantau semua perubahan yang terjadi pada file proyek. Lalu menyimpannya ke dalam database.

Sebelum menggunakan Git:

<img src="https://d33wubrfki0l68.cloudfront.net/71ed5b84cb44b653bfd07c85849cff210fdf5404/a2798/img/git/revisi-tanpa-git.png" alt="Revisi File tanpa Git">

Setelah menggunakan Git:

<img src="https://d33wubrfki0l68.cloudfront.net/6b9ec3079ab5698d7a74ddddbc7f691ee84417bf/ce8f5/img/git/database-git.png" alt="Revisi File dengan Git">

Apa perbedaannya?

Saat kita ingin menyimpan semua perubahan pada file, biasanya kita membuat file baru dengan “save as”. Lalu, file akan menumpuk dalam direktori proyek seperti pada ilustrasi di atas.

Tapi setelah menggunakan Git…

Hanya akan ada satu file dalam proyek dan perubahannya disimpan dalam database.

Git hanya akan menyimpan delta perubahannya saja, dia tidak akan menyimpan seluruh isi file yang akan memakan banyak memori.

Git memungkinkan kita kembali ke versi revisi yang kita inginkan.

Kenapa Git Penting Bagi Programmer?

<img src="https://d33wubrfki0l68.cloudfront.net/ae8014304e067f00673ed031c64037a02dc8dac8/8c18d/img/git/jutsu-kolaborasi.jpg" alt="Git untuk kolaborasi kode">

Jadi selain untuk mengontrol versi, git juga digunakan untuk kolaborasi.

Saat ini Git menjadi salah satu tool terpopuler yang digunakan pada pengembangan software open souce maupun closed source.

Google, Microsoft, Facebook dan berbagai perusahaan raksasa lainnya menggunakan Git.

Jadi, buat kamu yang punya impian ingin bekerja di sana, maka kamu harus bisa Git.

Selain itu, berikut ini ada beberapa menfaat yang akan kamu rasakan setelah bisa menggunakan Git.

1. Bisa menyimpan seluruh versi source code;
2. Bisa paham cara kolaborasi dalam proyek;
3. Bisa ikut berkontribusi ke poryek open-source;
4. Lebih aman digunakan untuk kolaborasi, karena kita bisa tahu apa yang diubah dan siapa yang mengubahnya.
5. Bisa memahami cara deploy aplikasi modern;
6. Bisa membuat blog dengan SSG.
7. dan sebagainya…


Itulah pembahasan mengenai pengertian dan pentingnya git bagi programmer yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai pengertian dan pentingnya git bagi programmer diatas mudah dipahami.
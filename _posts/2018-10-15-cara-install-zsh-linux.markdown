---
layout: post 
title: Cara Install zsh di Linux
date: 2018-10-15
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: my-zsh.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [zsh, Linux]
---

Z Shell atau lebih dikenal dengan nama zsh adalah sebuah interactive UNIX shell seperti halnya bash yang biasa kita pakai. Zsh sendiri sudah dikembangkan sejak 1990 oleh Paul Fastad.

Zsh menjadi salah satu shell yang cukup populer di Linux dan Mac OS X. Ia memiliki fitur-fitur yang kaya dan mudah diatur sesuai kebutuhan. Berikut beberapa kelebihan menggunakan zsh:

Auto-complete perintah CLI
Auto-complete path
Koreksi typo perintah CLI secara otomatis

Diartikel ini kita akan memasang Zsh bersama dengan Oh My Zsh di Ubuntu 16.04. Oh My Zsh sendiri merupakan framework untuk Zsh yang memiliki koleksi ratusan plugin dan themes dari komunitas yang tinggal pakai.

1. Konfigurasi Zsh

Pasang dulu Z shell untuk Ubuntu dengan memasukkan perintah berikut di terminal:

    sudo apt install zsh

Setelah terpasang, gantikan bash dengan zsh sebagai shell default:

    chsh -s /usr/bin/zsh

Logout, lalu login lagi untuk mengaktifkan shell yang baru ini. Saat membuka kembali aplikasi terminal, kita akan disambut Z Shell configuration function. Pesan ini akan muncul karena kita belum memiliki file konfigurasi zsh. Disini penulis memilih opsi (2) untuk mendapatkan konfigurasi bawaan yang direkomendasikan.


2. Konfigurasi Oh My Zsh

Setelah Z shell terpasang. Selanjutnya, kita akan melanjutkan dengan konfigurasi Oh My Zsh. Agar berjalan dengan lancar, pastikan git dan wget sudah terpasang. Jika belum, silahkan pasang dulu ketiganya dengan perintah:

    sudo apt install git wget

Selanjutnya salin kode berikut untuk mengunduh skrip pemasang Oh My Zsh dan menjalankannya:

    sh -c "$(wget https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh -O -)"

Jika berhasil, maka terminal kita akan menampilkan pesan:

<img src="https://static.cdn-cdpl.com/source/998b78e349061b4971c0a2b0e8d6be41/Screenshot_from_2018-02-22_18-43-26.png" alt="">

Sebelumnya saat memasang zsh, kita memilih untuk menggunakan konfigurasi bawaan yang direkomendasikan. Karena kita sekarang menggunakan Oh My Zsh, maka lebih baik jika kita menggunakan konfigurasi yang direkomendasikan olehnya. Ganti konfigurasi yang sudah ada dengan konfigurasi dari Oh My Zsh dengan perintah:

    cp ~/.oh-my-zsh/templates/zshrc.zsh-template ~/.zshrc
    source ~/.zshrc


Itulah pembahasan mengenai cara install zsh di Linux yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai cara install zsh di Linux diatas mudah dipahami.
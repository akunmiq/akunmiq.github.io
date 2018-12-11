---
layout: post 
title: Install KVM (Qemu) di Linux Ubuntu 16.04
date: 2018-12-11
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: kvm.jpeg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [KVM (Qemu), Linux]
---

Dalam artikel kita akan membahas tentang install KVM (Qemu) di linux ubuntu 16.04. Sebelum masuk ke langkah-langkah bagaimana menginstallnya, mari kita ketahui terlebih dahulu apa itu KVM (Qemu)?

KVM adalah singkatan dari Kernel-Based Virtual Machine, adalah perangkat lunak virtualisasi yang menyediakan kemampuan untuk menjalankan beberapa sistem operasi tamu dengan bantuan ekstensi virtualisasi perangkat keras. Mendukung berbagai macam sistem operasi tamu seperti Linux, Windows, Solaris, Haiku, REACT OS, dan banyak lagi. KVM dapat dikelola menggunakan baris perintah atau alat grafis yang tersedia.

Virt-Manager (Virtual Machine Manager) adalah aplikasi yang paling banyak digunakan untuk mengelola mesin virtual berbasis KVM, dan mendukung pembuatan, pengeditan, memulai dan menghentikan mesin virtual berbasis KVM, serta migrasi langsung atau dingin dari mesin tamu antar host .

Setelah mengetahui apa itu KVM (Qemu), sekarang kita akan masuk ke langkah-langkah untuk menginstall KVM (Qemu).

### Langkah pertama
Langkah pertama adalah kita akan menginstall KVM (Qemu) dengan command :

Pertama kita update terlebih dahulu :

	sudo apt-get update

lalu baru menginstall KVM :

	sudo apt-get install -y qemu-kvm qemu virt-manager virt-viewer libvirt-bin

Setelah menginstall kita bisa melakukan pengecekan apakah server kita memiliki opsi virtualisasi atau belum dengan command:

	cat /proc/cpuinfo | grep vmx

catatan: jika kita menggunakan intel kita gunakan command vmx, tapi jika kita menggunakan amd kita gunakan command svm

### Langkah kedua
Langkah kedua adalah kita akan mendownload OS

Disini saya ingin menggunakan OS linux alpine standard, dan link OS-nya bisa dilihat di bawah ini :

https://alpinelinux.org/downloads/

### Langkah ketiga
Langkah ketiga adalah kita akan membuat virtual machine, dengan command :

	sudo virt-install  --name=installalpine  --ram=1024  --vcpus=1  --cdrom=/home/miqdad/alpine-standard-3.8.1-x86_64.iso --os-type=linux --disk path=/home/miqdad/installalpine.dsk,size=4

Keterangannya adalah :

--name = nama untuk virtual machine

--ram = ukuran ram dalam satuan MB

--vcpus = jumlah cpu virtual

--cdrom = tempat kita menyimpan download-an OS dan nama file OS tersebut (iso)

--os-type = tipe OS yang kita download

--disk path = tempat kita ingin menginstall OS tersebut

--size = ruang penyimpanan untuk OS dalam satuan GB dan minimal 4GB

Itulah pembahasan mengenai install KVM (Qemu) di linux ubuntu 16.04 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai install KVM (Qemu) di linux ubuntu 16.04 diatas mudah dipahami.
---
layout: post 
title: Install Virtual Box di Linux Ubuntu 16.04
date: 2018-12-21
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: virtualbox.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Virtualbox, Linux]
---

Dalam artikel kita akan membahas tentang install virtual box di linux ubuntu 16.04. Sebelum masuk ke langkah-langkah bagaimana menginstallnya, mari kita ketahui terlebih dahulu apa itu virtual box?

Virtualbox adalah software gratis milik Oracle yang fungsi utamanya adalah mem-visualisasi-kan sebuah atau banyak Sistem Operasi (OS) di dalam Sistem Operasi utama kita.

Jadi kita tidak perlu punya banyak komputer untuk memakai atau menguji beberapa Sistem Operasi. Misalnya: OS utama kita adalah Ubuntu namun kita juga ingin merasakan OS lain yang digunakan teman kita yaitu ‘Centos’. Maka kita bisa menggunakan Virtualbox ini untuk menjalankan Centos tersebut tentunya dalam mode virtual alias simulasi.

Setelah mengetahui apa itu virtual box, sekarang kita akan masuk ke langkah-langkah untuk menginstall virtual box.

### Langkah pertama
Langkah pertama adalah kita akan menginstall bahan-bahan sebelum menginstall virtual box.

Pertama kita update terlebih dahulu :

	sudo apt-get update

lalu kita akan meng-Impor Oracle public key ke sistem kita dengan command:

	wget -q https://www.virtualbox.org/download/oracle_vbox_2016.asc -O- \| sudo apt-key add -

	wget -q https://www.virtualbox.org/download/oracle_vbox.asc -O- | sudo apt-key add -

Sekarang, kita perlu menambahkan Oracle VirtualBox PPA ke sistem Ubuntu. Kita dapat melakukan perintah ini dengan command:

	sudo add-apt-repository "deb http://download.virtualbox.org/virtualbox/debian `lsb_release -cs` contrib"

### Langkah kedua
Langkah kedua adalah kita akan menginstall virtual box.

Pertama kita update terlebih dahulu :

	sudo apt-get update

lalu kita baru menginstall virtual box, dengan command :

	sudo apt-get install virtualbox-5.2

### Langkah ketiga
Langkah ketiga adalah kita akan mengecek dan menjalankan virtual box yang baru kita download, dengan command :

	virtualbox

Itulah pembahasan mengenai install virtual box di linux ubuntu 16.04 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai install virtual box di linux ubuntu 16.04 diatas mudah dipahami.
---
layout: post 
title: Install Docker di Linux Ubuntu 16.04
date: 2018-12-11
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: docker-back.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Docker, Linux]
---

Dalam artikel kita akan membahas tentang install Docker di linux ubuntu 16.04. Sebelum masuk ke langkah-langkah bagaimana menginstallnya, mari kita ketahui terlebih dahulu apa itu Docker?

Docker adalah aplikasi yang membuatnya sederhana dan mudah untuk menjalankan proses aplikasi dalam sebuah wadah, yang seperti mesin virtual, hanya lebih portabel, lebih ramah sumber daya, dan lebih bergantung pada sistem operasi host.

Ada dua metode untuk menginstal Docker pada Ubuntu 16.04. Salah satu metode melibatkan menginstalnya pada instalasi sistem operasi yang ada. Yang lainnya melibatkan memintal server dengan alat bernama Docker Machine yang menginstal Docker secara otomatis di atasnya.

Setelah mengetahui apa itu Docker, sekarang kita akan masuk ke langkah-langkah untuk menginstall Docker.

### Langkah pertama
Langkah pertama adalah kita akan menginstall docker. Paket instalasi Docker yang tersedia di repository resmi Ubuntu 16.04 mungkin bukan versi terbaru. Untuk mendapatkan versi terbaru ini, install Docker dari repositori Docker resmi. Bagian ini menunjukkan kepada Anda bagaimana melakukan hal itu.

Pertama, perbarui daftar paket Anda yang sudah ada:

	sudo apt-get update

Selanjutnya, instal beberapa paket prasyarat yang memungkinkan untuk menggunakan paket melalui HTTPS:

	sudo apt install apt-transport-https ca-certificates curl software-properties-common

Kemudian tambahkan kunci GPG untuk repositori Docker resmi ke sistem Anda:

	curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

Tambahkan repository Docker ke sumber APT:

	sudo add-apt-repository “deb [arch=amd64] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable”

Selanjutnya update paket database dengan paket docker dari repo yang ditambahkan:

	sudo apt-get update

Pastikan Anda akan menginstal dari repo Docker bukan dari default Ubuntu 16.04 repo:

	apt-cache policy docker-ce

Jika berhasil maka akan keluar seperti ini:

<img src="/assets/img/docker1.png">

Selanjutnya install docker:

	sudo apt-get install -y docker -ce

Setelah itu bisa kita cek dengan command:

	sudo systemctl status docker

Maka akan keluar seperti ini:

<img src="/assets/img/docker2.png">

### Langkah kedua
Langkah kedua adalah Bekerja Dengan Docker Image

Kontainer Docker dibangun dari Docker image. Secara default, Docker menarik image-image ini dari Docker Hub, registri Docker yang dikelola oleh Docker, perusahaan di belakang proyek Docker. Siapa pun dapat menyimpan Docker image mereka di Docker Hub, sehingga sebagian besar aplikasi dan distribusi Linux yang Anda perlukan akan memiliki image yang dihosting di sana.

Sebagai contoh kita ingin menggunakan ubuntu di dalam docker, maka kita tinggal mengetikkan command:

	sudo docker pull ubuntu

Maka outputnya akan seperti ini:

	Output
	Using default tag: latest
	latest: Pulling from library/ubuntu
	6b98dfc16071: Pull complete
	4001a1209541: Pull complete
	6319fc68c576: Pull complete
	b24603670dc3: Pull complete
	97f170c87c6f: Pull complete
	Digest: sha256:5f4bdc3467537cbbe563e80db2c3ec95d548a9145d64453b06939c4592d67b6d
	Status: Downloaded newer image for ubuntu:latest

Untuk melihat image yang telah diunduh ke komputer Anda, lalu ketikan:

	sudo docker images

Jika ingin menggunakannya kita bisa menggunakan command:

	sudo docker run ubuntu

Maka outputnya akan seperti ini:

<img src="/assets/img/docker3.png">

catatan: Angka dan huruf unik setelah root itu adalah ID Countainer.

Sekarang kita bisa menggunakan ubuntu di countainer tersebut. Dan kita juga bisa menjalankan command2 yang ada pada ubuntu pada umumnya.

Itulah pembahasan mengenai install Docker di linux ubuntu 16.04 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai install Docker di linux ubuntu 16.04 diatas mudah dipahami.
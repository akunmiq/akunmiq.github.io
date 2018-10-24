---
layout: post 
title: Cara Penggunaan "Find" di Linux
date: 2018-10-23
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: linux-find.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Find, Linux]
---

Perintah “Find” adalah salah satu perintah yang paling penting dan banyak digunakan di sytems Linux. Perintah “Find” digunakan untuk mencari dan menemukan daftar file dan direktori berdasarkan kondisi yang ditentukan oleh user/pengguna. “Find” dapat digunakkan didalam berbagai kondisi seperti mencari file dengan hak akses (permission), pengguna (users), kelompok (groups), tipe data (file types), ukuran (size) dan kriteria lain yang memungkinkan.

Melalui artikel ini saya akan berbagi pengalaman sehar-hari dalam menggunakan perintah “find” dan bentuk-bentuk contoh penggunaanya. Misal saja kita sudah membuat file didalam directory /Documents dengan nama coba.txt. Langsung saja..

1.Mencari file berdasarkan nama pada direktori saat ini

Mencari semua file yang mengandung nama coba.txt didalam direktori saat ini.

	find -name "coba.txt"
	#./Documents/coba.txt

2.Mencari file berdasarkan nama didalam directory /Documents

Mencari semua file didalam directory /Documents dengan nama coba.txt

	find Documents/ -name "coba.txt"
	#./Documents/coba.txt

3.Mencari file berdasarkan nama namun kita lupa menaruh file tersebut dimana

Dan kita hanya ingat file tersebut bernama coba.txt. Jangan lupa ditambah tanda “/” sebagai tanda dari semua file yang kita inginkan dan metode ini membutuhkan hak akses root sehingga perlu ditambahkan "sudo" didepannya.

	sudo find / -name "coba.txt"
	#/home/Documents/coba.txt

4.Mencari file berdasarkan nama tanpa memperdulikan huruf Besar dan Kecil

Mencari semua file berdasarkan nama coba.txt dan mengandung huruf Besar dan Kecil di direktori /Documents. Dan kita perlu menambahkan huruf "i" sebelum command "name".

	find Documents/ -iname "coba.txt"
	#./Documents/coba.txt
	 ./Documents/Coba.txt
	 ./Documents/COBA.txt

5.Mencari file berdasarkan nama namun kita lupa nama file tesebut. 

Mencari nama semua file tersebut dan file tersebut berekstensikan ".txt". Serta kita perlu menambahkan tanda "* " sebgai gantinya.

	find -iname "*.txt"


Itulah pembahasan mengenai beberapa cara penggunaan find di linux yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai beberapa cara penggunaan find di linux diatas mudah dipahami.
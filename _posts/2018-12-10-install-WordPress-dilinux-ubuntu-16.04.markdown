---
layout: post 
title: Install WordPress di Linux Ubuntu 16.04
date: 2018-12-10
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: wordpress.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [WordPress, Linux]
---

Dalam artikel kita akan membahas tentang install WordPress di linux ubuntu 16.04. Sebelum masuk ke langkah-langkah bagaimana menginstallnya, mari kita ketahui terlebih dahulu apa itu WordPress?

WordPress adalah sebuah aplikasi sumber terbuka (open source) yang sangat populer digunakan sebagai mesin blog (blog engine). WordPress dibangun dengan bahasa pemrograman PHP dan basis data (database) MySQL. PHP dan MySQL, keduanya merupakan perangkat lunak sumber terbuka (open source software). Selain sebagai blog, WordPress juga mulai digunakan sebagai sebuah CMS (Content Management System) karena kemampuannya untuk dimodifikasi dan disesuaikan dengan kebutuhan penggunanya. WordPress adalah penerus resmi dari b2/cafelog yang dikembangkan oleh Michel Valdrighi. Nama WordPress diusulkan oleh Christine Selleck, teman Matt Mullenweg. WordPress saat ini menjadi platform content management system (CMS) bagi beberapa situs web ternama seperti CNN, Reuters, The New York Times, TechCrunch, dan lainnya.

Setelah mengetahui apa itu WordPress, sekarang kita akan masuk ke langkah-langkah untuk menginstall WordPress.

### Langkah pertama
Langkah pertama adalah kita akan menginstall apache2 dengan command :

	sudo apt-get install apache2

Pada langkah ini telah saya jelaskan langkah-langkah menginstallnya pada artikel sebelumnya, bisa dilihat pada link ini : https://miqdadhome.com/membuat-lokal-web-server-diubuntu-dengan-apache2/

### Langkah kedua
Langkah kedua adalah kita akan menginstall MySQL Database Server dan Client, dengan command :

	sudo apt-get install mysql-server mysql-client

Setelah menginstal MySQL, kamu akan disuruh untuk memasukkan password untuk root, pilihlah password yang bagus dan aman, setelah itu tekan ok 2x.

<img src="/assets/img/mysql-password.png">

Database server belum aman, karena alasan ini, berikan perintah berikut untuk memperkeras keamanannya:

	sudo mysql_secure_installation 

Selanjutnya akan muncul beberapa pertanyaan, jika anda tidak ingin mengubah password root, maka pilih N / no ketika muncul pertanyaan itu, dan pilih Y / yes untuk pertanyaan sisanya.

### Langkah ketiga
Langkah ketiga adalah kita akan menginstall PHP dan modul, dengan command :

	sudo apt-get install php7.0 php7.0-mysql libapache2-mod-php7.0 php7.0-cli php7.0-cgi php7.0-gd

Selanjutnya, untuk menguji apakah php bekerja dalam kolaborasi dengan server web, kita perlu membuat file info.php di dalam / var / www / html. Dengan command :

	sudo vi /var/www/html/info.php

Dan copy kode di bawah ini ke dalam file, simpan dan keluar.

	<?php 
	phpinfo();
	?>

Jika sudah selesai maka bisa kita cek dengan membuka web dibrowser dan ketikan localhost/info.php. Seharusnya kalian bisa melihat gambar seperti ini:

<img src="/assets/img/PHP-Information.png">

### Langkah keempat
Langkah keempat adalah kita akan menginstall WordPress, pertama kita harus mendownload paket lalu meng-ekstrak nya

	wget -c http://wordpress.org/latest.tar.gz
	
	tar -xzvf latest.tar.gz

Kemudian pindahkan file WordPress dari folder yang diekstrak ke direktori root default Apache, / var / www / html /:

	sudo rsync -av wordpress/* /var/www/html/

Selanjutnya, atur izin yang benar pada direktori situs web, yaitu memberikan kepemilikan file WordPress ke server web sebagai berikut:

	sudo chown -R www-data:www-data /var/www/html/

	sudo chmod -R 755 /var/www/html/

### Langkah kelima
Langkah kelima adalah kita akan membuat database WordPress

	sudo mysql -u root -p

Setelah itu kalian akan masuk ke shellnya mysql, lalu gunakan command dibawah ini :

	mysql> CREATE DATABASE wp_myblog;

	mysql> GRANT ALL PRIVILEGES ON wp_myblog.* TO ‘your_username_here’@’localhost’ IDENTIFIED BY ‘your_chosen_password_here’;

	mysql> FLUSH PRIVILEGES;

	mysql> EXIT;

Sekarang masuk ke /var/www/html/ dan rename wp-config-sample.php menjadi wp-config.php

	sudo mv wp-config-sample.php wp-config.php

Setelah itu rubah settingan di dalam file tersebut, perhatikan setinggan di bawah ini :

<img src="/assets/img/wp-5.png">

Setelah itu restart web server dan mysql service dengan command :

	sudo systemctl restart apache2.service

	sudo systemctl restart mysql,service

Buka browser lalu buka localhost maka kalian akan melihat tampilan selamat datang di WordPress, langkah terakhir adalah mensetting halaman WordPress kalian sesuai dengan selera kalian masing2.

Itulah pembahasan mengenai install WordPress di linux ubuntu 16.04 yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai install WordPress di linux ubuntu 16.04 diatas mudah dipahami.
---
layout: post 
title: Membuat dan Mengenal Samba Server
date: 2019-1-7
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: samba2.jpeg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [samba, Linux]
---

Dalam artikel kita akan membahas tentang membuat dan mengenal samba server. Sebelum masuk ke langkah-langkah bagaimana penggunaannya, mari kita ketahui terlebih dahulu apa itu samba server?

Samba server adalah program yang dapat menjembatani kompleksitas berbagai platform system operasi Linux(UNIX) dengan mesin Windows yang dijalankan dalam suatu jaringan komputer. Samba merupakan aplikasi dari UNIX dan Linux, yang dikenal dengan SMB(Service Message Block) protocol. Banyak sistem operasi seperti Windows dan OS/2 yang menggunakan SMB untuk menciptakan jaringan client/server. Protokol Samba memungkinkan server Linux/UNIX untuk berkomunikasi dengan mesin client yang mengunakan OS Windows dalam satu jaringan.

Atau bisa diartikan seperti sebuah software yang bekerja di sistem operasi linux, unix dan windows yang menggunakan protokol network smb (server massage block). Smb adalah sebuah protokol komunikasi data yang juga digunakan oleh Microsoft dan OS/2 untuk menampilkan fungsi jaringan client-server yang menyediakan sharing file dan printer serta tugas-tugas lainnya yang berhubungan.

Setelah mengetahui apa itu samba server, sekarang kita akan masuk ke langkah-langkah untuk membuat samba server.

## 1. Install Samba Server

### Langkah Pertama
Langkah pertama adalah kita akan mendownload 'samba server' terlebih dahulu dengan command:

	sudo apt install samba-client samba-common cifs-utils

### Langkah Kedua
Langkah kedua adalah kita akan edit file 'smb.conf' dengan command:

	nano /etc/samba/smb.conf

lalu tambahkan tulisan dibawah ini dibagian paling bawah

[global]
workgroup = WORKGROUP
server string = Samba Server %v
netbios name = ubuntu
security = user
map to guest = bad user
dns proxy = no

#============================ Share Definitions ============================== 

[Anonymous]
path = /samba/anonymous
browsable =yes
writable = yes
guest ok = yes
read only = no
force user = nobody

### Langkah Ketiga
Langkah ketiga adalah kita akan membuat folder baru dengan command:

	mkdir -p /samba/anonymous

### Langkah Keempat
Langkah keempat adalah kita akan mengganti permission file dengan command:

	sudo chmod -R 0775 /samba/anonymous

	sudo chown -R nobody:nogroup /samba/anonymous

### Langkah Kelima
Langkah kelima adalah kita akan restart samba server dengan command:

	sudo service smbd restart

### Langkah Keenam
Langkah keenam adalah kita akan menambahkan group dan user dengan command:

	sudo addgroup smbgrp

	sudo useradd till -G smbgrp

	sudo smbpasswd -a till

Lalu kita akan diminta untuk memasukkan password, bisa diisi sesuai keinginan kita.

### Langkah Ketujuh
Langkah ketujuh adalah kita akan membuat folder baru dengan command:

	sudo mkdir -p /samba/secured

### Langkah Kedelapan
Langkah kedelapan adalah kita akan mengganti pemission file dengan command:

	cd /samba

	sudo chmod -R 0770 secured
	
	sudo chown root:smbgrp secured

### Langkah Kesembilan
Langkah kedua adalah kita akan edit file 'smb.conf' dengan command:

	nano /etc/samba/smb.conf

Tambahkan baris berikut di akhir file:

[secured]
 path = /samba/secured
 valid users = @smbgrp
 guest ok = no
 writable = yes
 browsable = yes

### Langkah Kesepuluh
Langkah kesepuluh adalah kita akan restart samba server dengan command:

	sudo service smbd restart

## 2. Install Samba Client

### Langkah Pertama
Langkah pertama adalah kita akn install 'samba client' dengan command:

	sudo apt-get install samba-client samba-common cifs-utils

### Lanngkah Kedua
Langkah kedua adalah kita akan membuat samba client dengan command:

	sudo smbclient -I 192.168.100.115 -U user -L share

- 192.168.100.115 = ini bisa diisi sesuai dengan IP client kita.

### Langkah Ketiga
Langkah ketiga adalah kita akan membuat smbcredentials dengan command:

	cd /mnt

	sudo echo "username=user" >.smbcredentials

	sudo echo "password=123456" >> .smbcredentials

- username dan password bisa kita isi sesuai dengan keinginan kita.

### Langkah Keempat
Langkah keempat adalah kita akan mengganti permission file dengan command:

	sudo chmod 600 .smbcredentials

### Langkah Kelima
Langkah kelima adalah kita akan menambahkan IP client di /etc/fstab dengan command:

	sudo nano /etc/fstab

lalu tambahkan berikut pada bagian bawah lalu save.

//192.168.100.115/Anonymous /mnt/samba cifs credentials=/mnt/.smbcredentials,defaults 0 0 

- IP sesuai dengan IP client kita

### Langkah Keenam
Langkah keenam adalah kita akan mengemount samba dengan command:

	sudo mount -a

Jika kita 'umount -a' maka kita tidak akan bisa lagi melihat isi file client.

Itulah pembahasan mengenai membuat dan mengenal samba server yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai membuat dan mengenal samba server diatas mudah dipahami.
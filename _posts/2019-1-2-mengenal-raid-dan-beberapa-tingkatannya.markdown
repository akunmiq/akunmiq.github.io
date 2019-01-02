---
layout: post 
title: Mengenal RAID dan Beberapa Tingkatannya.
date: 2019-1-2
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: raid.jpg # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [RAID, Linux]
---

Dalam artikel kita akan membahas tentang mengenal RAID dan beberapa tingkatannya. Sebelum masuk ke langkah-langkah bagaimana penggunaannya, mari kita ketahui terlebih dahulu apa itu RAID?

RAID, singkatan dari Redundant Array of Independent Disks merujuk kepada sebuah teknologi di dalam penyimpanan data komputer yang digunakan untuk mengimplementasikan fitur toleransi kesalahan pada media penyimpanan komputer (utamanya adalah hard disk) dengan menggunakan cara redundansi (penumpukan) data, baik itu dengan menggunakan software, maupun unit perangkat keras RAID terpisah. RAID didesain untuk meningkatkan keandalan data dan/atau meningkatkan kinerja I/O dari hard disk. kali ini GemarOprek akan mengupas tuntas Mengenal Raid dan beberapa tingkatannya

Sejak pertama kali diperkenalkan, RAID dibagi ke dalam beberapa skema, yang disebut dengan “RAID Level” (tingkatan). Pada awalnya, ada lima buah RAID level yang pertama kali dikonsepkan, tetapi seiring dengan waktu, level-level tersebut berevolusi, yakni dengan menggabungkan beberapa level yang berbeda dan juga mengimplementasikan beberapa level proprietary yang tidak menjadi standar RAID.

Ada dua sistem perangkaian utama dalam RAID, yaitu stripping (penyalinan data ke lebih dari satu buah hard disk) dan mirroring (pemecahan data ke beberapa hard disk). Sistem stripping efektif untuk meningkatkan kecepatan akses data dan tulis data, sementara itu sistem mirroring cocok untuk backup data.

Setelah mengetahui apa itu RAID, sekarang kita akan masuk ke langkah-langkah untuk mengenal RAID dan beberapa tingkatannya.

## Tipe-tipe RAID

### Software RAID
Semua konfigurasi ditangani oleh sistem operasi/software. Keuntungan dari RAID software yang sangat murah, karena tidak perlu membeli perangkat keras tambahan untuk mengelola RAID. Tetapi karena tidak dikelola oleh hardware sendiri, maka kelemahannya adalah dia butuh sumber daya memori dan daya CPU tambahan dari komputer.

### Hardware RAID
Semua informasi tentang konfigurasi RAID disimpan dalam interface card dalam bentuk perangkat keras. Keuntungannya adalah meningkatkan kinerja. Karena semuanya ditangani oleh interface card, sehingga komputer tidak tidak perlu menggunakan memori atau daya CPU untuk menjalankan RAID.

Dulu sekali, **Hardware RAID** bisa dikatakan jadi primadona. Namun seiring berkembangnya waktu,  multi-core CPU dan memori sudah bisa didapatkan dengan harga yang semakin terjangkau dan semakin mumpuni kualitasnya. Maka dengan CPU yang lebih cepat, **Software RAID** pun sekarang bisa melakukan kinerja sebaik Hardware RAID dan bahkan bisa lebih cepat dalam beberapa kasus.

## Beberapa Tingkatan dalam RAID

### RAID 0
Dengan RAID 0, kita menggunakan dua / lebih hard disk yang bertindak seolah-olah mereka satu hard disk. Raid 0 diibaratkan memiliki  “0″ perlindungan. Bahkan karena kita menggunakan dua hard disk maka kita memiliki dua kali risiko kehilangan data. Karena bila salah satu drive mengalami error, maka kita terancam kehilangan data.

**Kelebihan:**

- RAID 0 menggunakan ruang hard disk secara maksimal karena tidak ada redundasi data.
- RAID 0 punya kecepatan yang lebih karena lebih banyak ruang dari dua hard disk yang dijadikan satu.

**Kekurangan:**

- Tidak ada perlindungan. Jadi jika kita kehilangan satu hard disk tunggal, data kita akan hilang.
- Karena kita menggunakan dua hard drive tanpa redundansi, maka resiko kita jadi dua kali lipat. Makanya akan lebih aman untuk menyimpan data dalam hard disk tunggal, misalnya bila kita menyimpan file 10MB dimana masing-masing drive menerima 5MB, maka jika salah satu drive rusak, kita hanya kehilangan data 5MB.

<img src="/assets/img/raid0.png">

### RAID 1
Dalam RAID 1 terjadi mirrorring antar hard disk. Sehingga dia menyediakan redundansi jika  salah satu disk mengalami error. Tidak seperti RAID 0 di mana semua space digabungkan, RAID 1 hanya menggunakan setengah ruang karena drive kedua digunakan untuk redundansi. Dengan syarat kedua hard drive ukurannya harus sama.

**Kelebihan:**

- Redundansi dan Kecepatan.

**Kekurangan:** 

-Space hard disk tidak digunakan secara efisien. Karena kedua hard disk adalah salinan satu sama lain, hanya setengah dari ukuran jumlah gabungan yang digunakan.

<img src="/assets/img/raid1.png">	

### RAID 2
RAID 2, juga menggunakan sistem stripping. Namun ditambahkan tiga harddisk lagi untuk pariti hamming, sehingga data menjadi lebihreliable. Karena itu, jumlah harddisk yang dibutuhkan adalah minimal 5 (n+3, n > 1). Ketiga harddisk terakhir digunakan untuk menyimpan hamming code dari hasil perhitungan tiap bit-bit yang ada di harddisk lainnya. **Contoh:**

Kita memiliki 5 harddisk (sebut saja harddisk A,B,C, D, dan E) dengan ukuran yang sama, masing-masing 40GB. Jika kita mengkonfigurasi keempat harddisk tersebut dengan RAID 2, maka kapasitas yang didapat adalah: 2 x 40GB = 80GB (dari harddisk A dan B). Sedangkan harddisk C, D, dan E tidak digunakan untuk penyimpanan data, melainkan hanya untuk menyimpan informasi pariti hamming dari dua harddisk lainnya: A, dan B. Ketika terjadi kerusakan fisik pada salah satu harddisk utama (A atau B), maka data tetap dapat dibaca dengan memperhitungkan pariti kode hamming yang ada di harddisk C, D, dan E.

<img src="/assets/img/raid2.png">

### RAID 3
RAID 3, juga menggunakan sistem stripping. Juga menggunakan harddisk tambahan untuk reliability, namun hanya ditambahkan sebuah harddisk lagi untuk parity.. Karena itu, jumlah harddisk yang dibutuhkan adalah minimal 3 (n+1 ; n > 1). Harddisk terakhir digunakan untuk menyimpan parity dari hasil perhitungan tiap bit-bit yang ada di harddisk lainnya. **Contoh kasus:**

Kita memiliki 4 harddisk (sebut saja harddisk A,B,C, dan D) dengan ukuran yang sama, masing-masing 40GB. Jika kita mengkonfigurasi keempat harddisk tersebut dengan RAID 3, maka kapasitas yang didapat adalah: 3 x 40GB = 120GB. Sedangkan harddisk D tidak digunakan untuk penyimpanan data, melainkan hanya untuk menyimpan informasi parity dari ketiga harddisk lainnya: A, B, dan C. Ketika terjadi kerusakan fisik pada salah satu harddisk utama (A, B, atau C), maka data tetap dapat dibaca dengan memperhitungkan parity yang ada di harddisk D. Namun, jika harddisk D yang mengalami kerusakan, maka data tetap dapat dibaca dari ketiga harddisk lainnya.

<img src="/assets/img/raid3.png">

### RAID 4
Sama dengan sistem RAID 3, namun menggunakan parity dari tiap block harddisk, bukan bit. Kebutuhan harddisk minimalnya juga sama, 3 (n+1 ; n >1).

<img src="/assets/img/raid4.png">

### Raid 5 (Disk Striping with Distributed Parity)
RAID 5 adalah tingkat atau level yang paling populer digunakan di server saat ini. Dengan RAID 5 kita bisa memiliki performa dan efisiensi penggunaan ruang. Dalam RAID 5 redundansi didistribusikan di antara semua drive. Jumlah minimum dari drive yang dapat digunakan pada RAID 5 adalah tiga.

**Kelebihan:**

- Efisiensi penggunaan kombinasi harddisk.
- Toleransi kesalahan: Jika  salah satu hard disk down/error  maka data tetap aman.

**Kekurangan:**

- Kecepatan RAID 5 tidak secepat RAID 0 atau 1.
- Jika lebih dari satu hard disk mengalami error, maka data terancam hilang.

<img src="/assets/img/raid5.png">

### Raid 6 (Disk Striping with Dual Parity)
RAID 6 pada dasarnya sama dengan RAID 5, dengan perbedaan dua drive bisa down pada saat yang sama bukan hanya satu. Jumlah minimum dari drive yang dapat digunakan dengan RAID 6 adalah empat.

**Kelebihan:**

- Meskipun dua hard disk down bersamaan, data kita tetap aman.

**Kekurangan:**

- Space total hard drive sangat berkurang karena lebih banyak dialokasikan untuk partisi redundansi.
- Kecepatan RAID 6 tidak secepat RAID 0 atau 1.
- Proses rebuilt lebih lambat. Ketika drive down, maka perlu rebuilt kembali. Kinerja akan menurun jauh bila dibandingkan dengan metode RAID lainnya.

<img src="/assets/img/raid6.png">

### Raid Z
Raid Z dan RAID Z2 adalah penemuan Sun Micro System. RAID Z memiliki semua manfaat dari RAID 5 dan fitur lainnya yang membuatnya jauh lebih unggul. Seperti dengan RAID 5, RAID Z dapat mendukung sejumlah hard disk yang bekerja sama dan satu disk untuk redudansi. Jumlah minimum dari hard disk adalah tiga dan hanya satu yang bisa down pada suatu waktu. Jika lebih dari satu hard disk rusak pada saat yang sama, maka kita beresiko kehilangan data.

**Kelebihan:** 

- Memiliki semua kelebihan dari RAID 5 dan fitur lainnya.

**Kelemahan:** 

- Hanya dapat digunakan dengan OS berbasis Open Solaris seperti Nexenta dan atau sistem berbasis BSD seperti FreeBSD.

<img src="/assets/img/raidz.png">

### Raid Z2
Raid Z2 hampir identik dengan Raid Z dan mirip dengan RAID 6. Dalam RAID Z2, meski dua hard disk bisa down di waktu bersamaan namun data akan tetap aman dan mudah diakses. Sama seperti RAID Z, RAID Z2 jauh lebih unggul dengan RAID 6 karena di dalamnya terdapat banyak fitur lainnya. Jumlah minimum drive untuk menggunakan RAID Z2 adalah empat.

**Kelebihan:**

- Data lebih aman meski dua drive bisa down pada saat yang sama bukan hanya satu.
- Memiliki semua manfaat dari RAID Z.

**Kekurangan:**

- Dua hard disk digunakan untuk paritas, sehingga ukuran jumlah gabungan space sangat terbatas.
- Hanya dapat digunakan dengan OS berbasis Open Solaris seperti Nexenta dan atau sistem berbasis BSD seperti FreeBSD.

<img src="/assets/img/raidz2.png">

### Raid 10
RAID 10 adalah gabungan dari  RAID 1 + RAID 0. Makanya dia bisa memberikan optimasi untuk toleransi kesalahan. Dimana RAID 0 memiliki kecepatan yang lebih karena lebih banyak ruang dari dua hard disk yang dijadikan satu, sedangkan RAID 1 memberikan mirroring disk untuk redundansi. Dalam beberapa kasus, RAID 10 menawarkan data yang lebih cepat membaca dan menulis daripada RAID 5 karena tidak perlu mengelola paritas. Minimum harddisk yang bisa digunakan adalah 4 hard disk.

**Kelebihan:**

- Memiliki manfaat dari kecepatan dari RAID 0 dan Mirroring dari Raid 1.
- Tingkat keamanan terhadap kemungkinan hilangnya data yang lebih baik dari penggunaan sebuah harddisk.

**Kekurangan:**

- Memiliki segala kekurangan yang dimiliki RAID 1 dan RAID 0.
- Kegagalan disk memiliki efek pada throughput, meskipun hal ini masih dapat ditoleransi.

<img src="/assets/img/raid10.png">

Itulah pembahasan mengenai mengenal RAID dan beberapa tingkatannya yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai mengenal RAID dan beberapa tingkatannya diatas mudah dipahami.
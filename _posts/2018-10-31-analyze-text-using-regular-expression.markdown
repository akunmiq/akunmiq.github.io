---
layout: post 
title: Analyze Text Using Regular Expression
date: 2018-10-31
description: You’ll find this post in your `_posts` directory. Go ahead and edit it and re-build the site to see your changes. # Add post description (optional)
img: analyze.png # Add image post (optional)
fig-caption: # Add figcaption (optional)
tags: [Analyze, Linux]
---

Dalam artikel kita akan membahas tentang Analyze text using regular expression. Langsung saja..

## Apa yang dimaksud dengan Analyze Text?

Analyze Text adalah cara untuk mencari sebuah kata yang kita inginkan. Command ini hampir mirip dengan command 'find'.

#### Yang pertama

	grep '^The' TEST.txt

<img src="/assets/img/grep1.png">

Tanda (^) sebagai alat untuk mencari kata yang kita inginkan. Pada command ini kita ingin mencari kata 'The' pada awal kalimat.

#### Yang kedua

	grep '^T[a-z][^a]' TEST.txt 

<img src="/assets/img/grep2.png">

Pada command ini kita ingin mencari kata yang berawalan 'T' dan huruf selanjutnya dari 'a-z' dan huruf selanjutnya kecuali huruf 'a'. Tanda [^a] berarti kita menginginkan huruf yang kita cari selain huruf 'a'.

#### Yang ketiga

	grep '\<[Tt]he\>' TEST.txt

<img src="/assets/img/grep3.png">

Pada command ini kita ingin mencari kata 'the' yang tidak pengaruh huruf besar maupun kecil. Dan comand ini akan mencari kata tersebut tidak hanya diawal kalimat dan akan mencari ditengah kalimat.

#### Yang keempat

	grep '\([a-z][a-z]\)' TEST.txt

<img src="/assets/img/grep4.png">

Pada command ini kita ingin mencari kata yang huruf pertama dan kedua adalah huruf 'a-z'. Dan command ini tidak berlaku jika huruf tersebut huruf kapital. 


Itulah pembahasan mengenai Analyze Text Using Regular Expression yang harus anda ketahui sebagai pengguna komputer. Meskipun kalah dengan sistem operasi windows dalam hal kepopulerannya, pengguna linux juga tergolong cukup banyak, terutama bagi yang bekerja dalam bidang jaringan. Semoga artikel mengenai Analyze Text Using Regular Expression diatas mudah dipahami.
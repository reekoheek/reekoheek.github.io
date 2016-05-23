---
layout: post
title: Mencicipi Bono 2
tags: [Teknologi]
---

Bono adalah sebuah framework untuk pembangunan aplikasi web yang kami kembangkan di PT Sagara Xinix Solusitama.

## Kebutuhan Sistem
  node.js
  yeoman
  bower
  gulp
  generator-bono-2
  composer
  php-cli

## Instalasi Kebutuhan Sistem

Install node.js dari https://nodejs.org
Install composer dari https://getcomposer.org
Install php-cli

Install kebutuhan sistem sisanya melalui terminal dengan menjalankan perintah-perintah di bawah ini,

```bash
npm i yo -g
npm i bower -g
npm i gulp -g
npm i generator-bono-2 -g
```

## Inisialisasi project baru

Berikut ini untuk menginisialisasi project baru dengan menggunakan yeoman bono-2 generator.
Inisialisasi akan sukses dengan asumsi kebutuhan sistem telah tersedia dan dapat diakses dari PATH

```bash
mkdir app
cd app
yo bono-2
```

Lalu ikuti dan jawab pertanyaan2 yang muncul, (bisa di-enter2 saja)

Lalu eksekusi perintah berikut untuk instalasi pustaka-pustaka PHP dan Bower

```bash
npm i
gulp install
```

Lalu untuk menggunakan php-cli sebagai server

```bash
gulp
```
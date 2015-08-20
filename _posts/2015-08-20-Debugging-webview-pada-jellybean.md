---
layout: post
title: Debugging WebView pada Android Jellybean
tags: [Mobile,Web,Teknologi]
---

Penggunaan webview pada android saat ini memang sudah mulai diberdayakan secara masif untuk pengembangan aplikasi mobile berbasis html5 ataupun hybrid. Khususnya pada pengembangan aplikasi android, Google telah menyediakan tool yang merupakan andalan para pengembang web yaitu [Remote Debugging pada Android](https://developer.chrome.com/devtools/docs/remote-debugging) dengan Chrome. Tapi sayangnya fitur ini hanya bisa digunakan untuk android mulai versi Kitkat. Sayangnya pengguna android berversi Jellybean masih sangat banyak di dunia, sehingga para developer lebih baik tidak meninggalkan user based yang masih sangat besar ceruknya ini. Berikut di bawah ini adalah beberapa tools yang bisa digunakan untuk melakukan debugging pada saat pengembangan aplikasi mobile berbasis webview pada android Jellybean.

## adb logcat

Secara ofisial dari Google, pengembangan untuk versi android terdahulu seperti Jellybean memaksa developer untuk menggunakan tool standar seperti adb logcat untuk menampilkan log dari android. Untuk menggunakan adb logcat, kita perlu untuk menginstall adb melalui [Android SDK yang dapat didownload di sini](http://developer.android.com/sdk/index.html). Distribusi Linux yang terbaru kemungkinan telah memiliki pada repositoriesnya. Anda dapat menginstal melalui repositories jika diinginkan. Untuk mempelajari lebih lanjut mengenai adb dapat dilihat [di sini](http://developer.android.com/tools/help/adb.html)

Setelah instalasi selesai dilakukan, pastikan device terhubung atau emulator telah dihidupkan dengan cara:

```bash
adb devices
```

Lalu jalankan logcatnya

```bash
adb logcat | grep Console
```

Dengan teknik adb logcat ini, kita hanya bisa melihat output dari console.* dari javascript. 

## JSConsole

Buka dengan browser anda url http://jsconsole.com, lalu ketik `:listen`. Kemudian akan tercetak berikut ini,

```
Connected to "xxxxxxxx-42F7-4850-A3FF-E55386B44B3B"
<script src="http://jsconsole.com/remote.js?xxxxxxxx-42F7-4850-A3FF-E55386B44B3B"></script>
```

Copy paste `<script>..</script>` pada halaman web yang ingin di-inspect.

Teknik-teknik di atas hanya mampu untuk meng-inspect Javascript. Dibandingkan apa yang bisa kita lakukan melalui Chrome Remote Debugging Tool untuk device-device Kitkat dan di atasnya, hal ini tentunya kurang memuaskan. Untuk itu ada alternatif lain yang bisa gunakan.

## Weinre

[Weinre](http://people.apache.org/~pmuellr/weinre-docs/latest/)  adalah Web Inspector Remote, sebuah debugger untuk halaman web seperti Firebug (Firefox), Web Inspector (Webkit-based browser), kecuali hal ini bisa dijalankan secara remote. Untuk menggunakan Weinre silakan [menginstall](http://people.apache.org/~pmuellr/weinre-docs/latest/Installing.html) terlebih dahulu.

Untuk menghidupkan Weinre server ketik baris perintah berikut pada terminal,

```
weinre --boundHost -all-
``` 

Pastikan port 8080 tidak digunakan sebelumnya karena Weinre akan listen pada port tersebut. Setelah weinre server menyala, kita dapat mengakses `http://localhost:8080/` untuk mengakses antarmuka debugger berbasis web

## JSHyBugger

[JSHyBugger](https://www.jshybugger.com/) mungkin debugger terbaik untuk Android berbasis Jellybean ke bawah. Anda bisa mencoba menggunakan JSHyBugger selama 2 menit per sesi dan jika suka bisa menonaktifkan limitasi tersebut dengan membeli lisensi. Cara penggunaannya bisa dilihat pada [halaman webnya berikut ini](https://www.jshybugger.com/#!/download).

Dengan rilisnya Android M dalam beberapa hari/bulan, penggunaan Android Jellybean mungkin akan berkurang cukup signifikan. Nikmati masa-masa development dengan Jellybean hingga masa itu datang dengan tool-tool yang saya paparkan di sini.

Happy Coding!









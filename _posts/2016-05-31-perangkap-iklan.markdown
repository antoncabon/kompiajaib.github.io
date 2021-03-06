---
layout: post
title: "Perangkap Iklan Pihak Ketiga"
subtitle: "Tanpa diketahui ternyata provider meng-inject iklan."
description: "Ternyata tanpa kita ketahui, provider yang kita gunakan meng-inject iklan. Untuk itu kita buat perangkap iklannya."
date: 2016-05-31 07:00:00
author: "Adhy Suryadi"
tags: [ Blogging ]
header-img: "img/post/ads-on-internet.jpg"
image: "img/post/ads-on-internet.jpg"
---

> Selama ini saya tidak menyadari bahwa iklan yang sering saya lihat dan cukup mengganggu ternyata iklan dari provider yang saya gunakan.

## Iklan Provider

Sudah beberapa bulan belakangan ini saya menggunakan jaringan Indiehome dari Telkom untuk koneksi internet saya, namun belakangan ini saya baru menyadari bahwa Telkom meng-inject sebuah iklan ke halaman web yang kita buka. Sebenarnya kemunculan iklan tersebut tidak mengganggu tampilan web, namun pemuatan atau loading iklannya itu yang saya rasa cukup mengganggu.

Iklan tersebut akan muncul di atas atau di bawah halaman web dengan mendorong halaman web ke atas atau ke bawah seperti gambar di bawah ini.

![Iklan Telkom](data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs= "Iklan Telkom"){: data-src="{{ site.baseurl }}/img/post/iklan-telkom.jpg" width="750" height="439"}

Dan ini source code iklan tersebut (jika Anda menggunakan provider Indihome atau mungkin layanan Telkom lainnya) yang akan muncul di atas kode `</body` dari web yang kita kunjungi.

![Script Iklan Telkom](data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs= "Script Iklan Telkom"){: data-src="{{ site.baseurl }}/img/post/iklan-telkom-2.jpg" width="750" height="326"}

## Membuat Perangkap Iklan Pihak Ketiga

Nah, karena kemunculan iklan ini cukup menggangu loading halaman web ketika pengunjung yang datang menggunakan jaringan Indihome Telkom, maka kita perlu membuat perangkap script yang di-inject oleh pihak ketiga sepert iklan Telkom tersebut agar tidak mengganggu pengunjung baik loading maupun iklannya.

Caranya cukup mudah, silahkan ganti kode `</body>` dengan kode di bawah ini:

```
<!--</body>--></body>
```
Dan untuk Blogger menggunakan kode seperti di bawah ini:

```
&lt;!--</body>--&gt;&lt;/body&gt;
```

Dengan begitu maka script iklan pihak ketiga akan terperangkap dalam komentar `<!-- -->` yang otomatis tidak akan berfungsi seperti gambar di bawah ini.

![Script Iklan Telkom](data:image/png;base64,R0lGODlhAQABAAD/ACwAAAAAAQABAAACADs= "Script Iklan Telkom"){: data-src="{{ site.baseurl }}/img/post/iklan-telkom-3.jpg" width="750" height="137"}

Silahkan cek kode HTML blog Anda, jika sudah menggunakan kode di atas berarti loading blog Anda tidak akan terganggu loading iklan Telkom ini jika pengunjung blog menggunakan jaringan layanan Telkom.

Namun untuk pengguna Blogger, hal ini juga bisa menyembunyikan widget.js dari Blogger sehingga widget sepert arsip, statistik, contact form, dan lainnya yang terintegrasi dengan widget.js Blogger menjadi tidak berfungsi. Namun tidak perlu khawatir karena hal ini bisa diatasi, silahkan cari cara mengatasinya di blog Kompi Ajaib.

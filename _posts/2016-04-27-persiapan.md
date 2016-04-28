---
layout:     post
title:      Persiapan dengan GTK+
date:       2016-04-27 12:52:56 +0700 
category: getting-started
---

Ketika sudah memahami mengenai GTK+ langkah selanjutnya adalah hal-hal apa saja yang perlu dipersiapkan untuk membangun aplikasi menggunakan pustaka GTK+.

### Memasang GTK+ Devel

Yakni pustaka GTK+ itu sendiri. Ada berbagai macam cara untuk memasangnya di setiap sistem operasi berbeda beda. Akan tetapi sementara di sini, saya mencontohkan pemasangan GTK+ _devel_ bagi Anda pengguna `GNU/Linux` untul disro `Ubuntu` dan `Archlinux` beserta derivatifnya.

#### Pengguna `Ubuntu` dan derivatifnya.

```
sudo apt-get install gnome-devel
```

#### Pengguna `Archlinux` dan derivatifnya.

```
sudo pacman -S gtk3
```

### Pemahaman Bahasa Pemrograman

Diharapkan pembaca sudah memahami dan menguasai dasar-dasar bahasa pemrograman C, jika belum lebih baik pelajarinya terlebih dahulu agar langkah-langkah yang ada di sini tidak menyulitkan, karena secara garis besar di situs ini tidak akan menjelaskan baris kode mengenai C, akan tetapi fokus pada GTK+ nya saja.

Berlaku pula dengan bahasa pemrograman lainnya, akan tetapi fokus tulisan perdana di situs GTK+ ini adalah dengan bahasa pemrograman C terlebih dahulu baru kemudian bahasa pemrograman lainnya.

### IDE atau Text Editor pendukung

Untuk IDE Anda bisa mengguanakan `Gnome Builder` (**disarankan**) atau `Code Blocks` untuk aplikasi _text editor_ Anda bisa menggunakan `Geany` (**disarankan**), `Gedit`, dan lain sebagainya.

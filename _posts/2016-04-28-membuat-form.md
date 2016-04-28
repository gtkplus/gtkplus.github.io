---
layout:     post
title:      Langkah Awal Membuat Form dengan GTK+
date:       2016-04-28 08:29:03 +0700 
category: getting-started
---

Untuk memahami apa itu GTK+ ada kiranya kita langsung saja praktek menerapkan GTK+ ke dalam sumber kode dimulai dari yang paling sederhana yakni membuat `form` terlebih dahulu, beserta penjelasannya.

## Praktek Membuat _Form_

Langsung saja praktek, pertama-tama Anda buat berkas dengan nama misalnya `form.c`, lalu _copy-paste_ kan kode di bawah ini:

<script src="https://gist.github.com/aliterm/ce663549b880c492d93aa11f47847f3e.js"></script>

### Compile

setelah itu simpan dan buka `terminal` lalu _compile_ kode di atas dengan perintah berikut:

```
gcc `pkg-config --cflags gtk+-3.0` -o form_sederhana form.c `pkg-config --libs gtk+-3.0`
```

### Screenshot

Berikut ini hasilnya ketika kode sumber telah dikompilasi dengan `gcc`:
[![alt Form](/images/form_sederhana.png "Form Sederhana dengan GTK+")](/images/form_sederhana.png){: .fancybox}

## Penjelasan Kode

Pada baris awal, jika kita ingin menggunakan GTK+ maka wajib diawali dengan `#include <gtk/gtk.h>`. Kemudian untuk memanggil _class application_ diperlukan sebuah variabel yang mengambil nilai dari `GtkApplication`. Contoh di atas saya menggunakan variable `app` yakni `GtkApplication *app;`

Kemudian untuk kode `app = gtk_application_new ("org.gtk.example", G_APPLICATION_FLAGS_NONE);` sintak dari [gtk_application_new](https://developer.gnome.org/gtk3/stable/GtkApplication.html#gtk-application-new) adalah sebagai berikut:

```
gtk_application_new (const gchar *application_id,
                     GApplicationFlags flags);
``` 

`gchar` sebenaranya `char` standar dari bahasa C, `GApplicationFlags` memiliki banyak nilai Anda bisa lihat sendiri semua nilainya [di sini](https://developer.gnome.org/gio/unstable/GApplication.html#GApplicationFlags). Pada contoh di atas saya menulis nilai dari `application_id` dengan `org.gtk.example`. Sebernarnya ini bebas mau diisi dengan apapun asalkan penulisanya mengikuti format DNS, dengan tanda titik di antara kata, contohnya seperti `aplikasi.saya`. Meskipun dapat ditulis dengan sembarang, akan tetapi para pengembang Gnome menyarankan guna untuk menjadikan aplikasi yang baik ialah seperti berikut. (baca: <https://developer.gnome.org/ChooseApplicationID/>)

Lalu kode `g_signal_connect (app, "activate", G_CALLBACK (activate), NULL);`. [g_signal_connect](https://developer.gnome.org/gobject/stable/gobject-Signals.html#g-signal-connect) bermaksud memberikan sinyal kepada aplikasi, ketika `activate` maka akan memanggil `function activate` kita bisa lihat dikode atasnya yakni pada ini:

```
static void
activate (GtkApplication* app,
          gpointer        user_data)
{
  ...
  ...
}
```

Kemudian kode `status = g_application_run (G_APPLICATION (app), argc, argv);` atau [g_application_run](https://developer.gnome.org/gio/stable/GApplication.html#g-application-run) yakni untuk menjalankan aplikasi gtk tersebut, diambil dari hasil variabel _class_ `app`.

Langsung kebagian atas yakni isi dari `function activate` yakni:

```
GtkWidget *window;
window = gtk_application_window_new (app);
```

Kode tersebut berfungsi untuk membuat `window` atau yang kita kenal sebagai `form`. Kemudian kode ` gtk_window_set_default_size (GTK_WINDOW (window), 200, 200);` mengidentifikasikan bahwa secara asali (_default_) `window` dibuat berkuran `200 width dan 200 hight pixel`. Lalu yang terakhir kode `gtk_widget_show_all (window);` yakni untuk menampilakn seluruh `widget` yang berada dalam `form` tersebut.

## Sumber Kode

Sumber kode di atas dapat Anda unduh dan pelajari di [GitHub GTK+ Indonesia](https://github.com/gtkplus) berikut sumber kodenya:

[Unduh kode sumber](https://github.com/gtkplus/examples/blob/master/membuat%20form/form.c){: .btn .btn-primary}
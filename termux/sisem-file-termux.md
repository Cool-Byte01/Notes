# Sistem File Termux

Termux tidak sesuai dengan FHS. Inilah sebabnya mengapa Termux tidak menggunakan paket Debian atau Ubuntu resmi untuk lingkungannya.

Termux tidak mengikuti Standar Hirarki Filesystem tidak seperti mayoritas distribusi Linux. Anda tidak dapat menemukan direktori seperti / bin, / etc, / usr, / tmp dan lainnya di lokasi yang biasa. Dengan demikian, semua program harus ditambal dan dikompilasi ulang untuk memenuhi persyaratan lingkungan Termux jika tidak mereka tidak akan dapat menemukan file konfigurasi atau data lainnya.

### Struktur File System Termux

```plaintex
Struktur Dasar Sistem File Termux

/data/data/com.termux/files
├── home
└── usr
```

Pada Termux struktur file dan direktori disusun dalam bentuk hiarki(satu direktori tertinggi membawahi file atau direktori lain). Ini mirip dengan Linux, ingat hanya **mirip** bukan **sama**. Karena Termux itu bukan distro Linux.

#### Struktur File Prefix

```plaintex
/data/data/com.termux/files/usr
├── bin
├── etc
├── include
├── lib
├── libexec
├── share
├── tmp
└── var
```

- `data/data/com.termux/files/usr/` atau `$PREFIX` : Berisi paket dan biner yang diinstal, setara dengan direktori `/usr/` di Linux. Di sinilah aplikasi dan perintah yang Anda instal melalui Termux disimpan.

- `/bin/` : Menampung biner perintah esensial seperti `ls`, `cp`, dan `mv`. Direktori ini berisi perintah dasar yang digunakan untuk navigasi dan manipulasi file.

- `/etc/` : Menyimpan file konfigurasi sistem. Jika Anda perlu mengubah pengaturan aplikasi atau sistem, file konfigurasi yang relevan biasanya berada di sini.

- `/tmp/` : Digunakan untuk file sementara. File yang disimpan di sini biasanya bersifat sementara dan dapat dihapus setelah sesi berakhir atau setelah beberapa waktu.

- `/var/` : Berisi data variabel seperti log dan cache. Log aplikasi dan data sementara lainnya disimpan di sini.

- `/opt/` : Dicadangkan untuk paket perangkat lunak opsional. Jika Anda menginstal perangkat lunak tambahan yang tidak termasuk dalam paket standar, mereka mungkin ditempatkan di sini.

### Struktur File Home

```plaintex
/data/data/com.termux/files/home
├── bin/
├── storage
│   ├── dcim -> /storage/emulated/0/DCIM
│   ├── downloads -> /storage/emulated/0/Download
│   ├── external-1 -> /storage/sdcard1/Android/data/com.termux/files
│   ├── movies -> /storage/emulated/0/Movies
│   ├── music -> /storage/emulated/0/Music
│   ├── pictures -> /storage/emulated/0/Pictures
│   └── shared -> /storage/emulated/0
└── .termux/
└── .config/
```

- `/data/data/com.termux/files/home/` atau `$HOME` : Ini adalah direktori home Anda, tempat Termux memulai secara default. Setara dengan direktori `/home/username/` di Linux, di sinilah Anda menyimpan file pribadi dan proyek Anda.

- `~/storage/` : Memberikan akses ke penyimpanan bersama di perangkat Android Anda, termasuk penyimpanan internal dan kartu SD. Untuk mengaksesnya, Anda perlu memberikan izin dengan menjalankan perintah `termux-setup-storage`.

- `~/bin/` : Merupakan symlink yang merujuk pada Untuk menyimpan file executable _(program)_ yang dapat dibuat atau dijalankan oleh user.

- `.termux` : Berisi file konfigurasi Termux yang dapat di ubah sesuai kebutuhan user.

- `.config` : Seperti `/usr/etc` direktori `.config` digunakan untuk mengkonfigurasi package _(aplikasi)_ atau sistem yang berlaku secara **lokal**. Sedangkan `/usr/etc` untuk mengkonfigurasi secara **global**.

> [!NOTE]
> Opsional jika Anda menggunakan `pacman`.
>
> - `/etc/pacman.conf` : Berisi pengaturan konfigurasi untuk pacman, termasuk informasi repositori dan opsi konfigurasi lainnya. Anda dapat mengedit file ini untuk menambahkan repositori tambahan atau mengubah perilaku pacman.
> - `/var/lib/pacman/` : Menyimpan basis data paket yang diinstal dan informasi repositori. Direktori ini penting untuk melacak status paket yang diinstal dan tersedia.

Memahami struktur ini akan membantu Anda menavigasi dan mengelola file serta direktori dalam Termux dengan lebih efisien.

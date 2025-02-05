# Belajar Perintah Linux Dengan Man Pages

<!-- mtoc-start -->

- [Perintah Dasar Man Pages](#perintah-dasar-man-pages)
  - [Opsi Man Pages](#opsi-man-pages)
  - [Section Man Pages](#section-man-pages)
    - [Penggunaan man pages dengan section](#penggunaan-man-pages-dengan-section)
  - [Navigasi Man Pages](#navigasi-man-pages)
  - [Cara Install Man Pages Di Termux](#cara-install-man-pages-di-termux)
  - [Sumber](#sumber)

<!-- mtoc-end -->

Man pages (Manual Pages) adalah dokumentasi resmi untuk perintah-perintah, fungsi, dan sistem operasi Linux. Berikut cara menggunakan man pages.

### Perintah Dasar Man Pages

1. Buka terminal Linux atau Termux.
2. Ketik `man <opsi> <perintah>` untuk melihat dokumentasi perintah tersebut.
   Contoh: `man ls` untuk melihat dokumentasi perintah `ls`.

### Opsi Man Pages

Beberapa opsi yang bisa digunakan pada man pages:

| Opsi           | Fungsi                                      |
| -------------- | ------------------------------------------- |
| `-a` (all)     | Menampilkan semua manual                    |
| `-f` (whatis)  | Menampilkan deskripsi singkat               |
| `-k` (search)  | Mencari manual berdasarkan kata kunci       |
| `-h` (help)    | Menampilkan bantuan                         |
| `-m` (manual)  | Menampilkan man pages secara spesifik       |
| `-s` (section) | Menampilkan man pages dari section tertentu |
| `-v` (verbose) | Menampilkan informasi versi                 |

### Section Man Pages

Section pada man pages adalah untuk mengkategorikan informasi dalam man pages. Dengan section, pengguna dapat menentukan bagian mana dari manual yang ingin dilihat.

| Section | Fungsi                                    |
| ------- | ----------------------------------------- |
| 1       | General commands (tools and utilities)    |
| 2       | System calls and error numbers            |
| 3       | Library functions                         |
| 3p      | perl(1) programmer's reference guide      |
| 4       | Device drivers                            |
| 5       | File formats                              |
| 6       | Games                                     |
| 7       | Miscellanea                               |
| 8       | System maintenance and operation commands |
| 9       | Kernel internals                          |

##### Penggunaan man pages dengan section

syntax dasar: `man <nomor section> <perintah>` atau `man -s <nomor section> <perintah>`

Contoh:

- `man 5 fstab` untuk melihat dokumentasi file formats(5) fstab
- `man -s 2 open` untuk melihat dokumentasi system calls(2) open

### Navigasi Man Pages

1. Scroll ke atas/bawah: `↑/↓`
2. Scroll ke kiri/kanan: `←/→`
3. Keluar: `q`
4. Cari kata: `/kata_kunci`
5. Pergi ke bagian tertentu: [nomor section](#section-man-pages)

### Cara Install Man Pages Di Termux

Man pages juga dapat digunakan di termux, berikut cara install man pages di Termux:

- pkg: `pkg install man`

- apt: `apt install man`

- pacman: `pacman -S man`

Cara penggunaan man pages di Termux juga sama seperti di Linux.

> [!TIP]
>
> 1. Gunakan `man -k` untuk mencari perintah terkait.
> 2. Gunakan `man -a` untuk melihat semua man pages.
> 3. Simpan halaman man pages dengan perintah `man -t <perintah> | col -b > file.txt`.

Untuk informasi lebih lanjut bisa dibaca di dokumentasi man pages dengan perintah `man -as 1 man`. Selain lewat terminal, man pages juga dapat diakses secara online di website [man7.org](https://man7.org/linux/man-pages/index.html).

Dengan menggunakan man pages, Kamu dapat memahami penggunaan perintah Linux atau Termux dengan lebih baik.

### Sumber

- dokumentasi man pages
- [linkedin](https://www.linkedin.com/pulse/reading-manual-pages-linux-man-command-anshul-agarwal-otcfc#:~:text=The%20man%20command%20in%20Linux,syntax%2C%20options%2C%20and%20examples.)

- [geeksforgeeks](https://www.geeksforgeeks.org/man-command-in-linux-with-examples/)

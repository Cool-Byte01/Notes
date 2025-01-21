# Perintah ls

`ls` digunakan untuk melihat daftar file dan direktori yang terdapat pada sebuah direktori (saat ini yang kamu buka). Perintah ini juga dapat digunakan untuk melihat informasi tentang file dan direktori, seperti izin, pemilik, gruop dan lain - lain.

## Syntax Dasar ls

`ls <opsi> <file/direktori>`

## Opsi Perintah ls

| Opsi   | Deskripsi                                                                               |
| ------ | --------------------------------------------------------------------------------------- |
| **-l** | Untuk memanampilkan informasi detail dari suatu file dan direktori.                     |
| **-a** | Untuk memanampilkan semua file dan direktori yang tersembunyi.                          |
| **-t** | Untuk mengurutkan file dan direktori yang terakhir dimodifikasi.                        |
| **-r** | Untuk melihat daftar file dan direktori secara terbalik.                                |
| **-S** | Untuk mengurutkan file dan direktori dari yang paling besar ukurannya.                  |
| **-R** | Untuk melihat daftar file dan direktori yang ada didalam subdirektori.                  |
| **-i** | Untuk melihat inode (nomor index) dari file atau direktori.                             |
| **-g** | Untuk melihat kepemilikan gruop atas file dan direktori.                                |
| **-h** | Untuk memanampilkan ukuran file dan direktori dengan format yang dapat di baca manusia. |
| **-d** | Untuk melihat daftar direktori itu sendiri, bukan isinya.                               |

> [!INFO]
> Refrensi:
>
> - [Geeksforgeeks; ls linux commands](https://www.geeksforgeeks.org/ls-command-in-linux/)
> - Man pages: `man ls`

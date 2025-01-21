# Perintah pwd

`pwd` _(print working directory)_ perintah ini digunakan untuk menampilkan path direktori kerja saat ini, yang dimulai dari akarnya (root direktori). Direktori kerja _(working direktori)_ adalah direktori yang saat ini kita buka.

## Syntax Dasar

`pwd <opsi/flags>`

Perintah ini tidak memiliki opsi ataupun argumen, tetapi dapat menerima _flags_(tanda) untuk perilaku tertentu.

## Flags pwd

| Flags  | Deskripsi                    |
| ------ | ---------------------------- |
| **-L** | Menampilkan path _symbolic_. |
| **-P** | Menampilkan path _actual_.   |

Secara default `pwd` menggunakan flag `-L`.

### Penejelasan Flags Lebih Lanjut

- **Path Symbolic(-L)**: Merujuk pada lokasi file atau direktori yang terlihat oleh user, dengan menggunakan jalur simbolik link atau pengalihan. Contoh: `~/Documents/` (simbolik link ke `/home/user/Documents`).

- **Path Actual(-P)**: Merujuk pada lokasi file atau direktori asli tanpa simbolik link atau pengalihan. Contoh: `/home/user/Documents`.

## Contoh Cara Penggunaan

1. `pwd`

```bash
~/storage/shared/ $ pwd
/data/data/com.termux/files/home/storage/shared
```

2. `pwd -L`

```bash
~/storage/shared/ $ pwd -L
/data/data/com.termux/files/home/storage/shared
```

3. `pwd -P`

```bash
~/storage/shared/ $ pwd -P
/storage/emulated/0
```

> [!INFO]
> Refrensi:
>
> - [geeksforgeeks; pwd command](https://www.geeksforgeeks.org/pwd-command-in-linux-with-examples/)

# Cara Menggunakan Pacman Di Termux

Disini Saya akan memberikan tutorial bagaimana caranya menggunakan Pacman di Termux.

### Langkah Pertama

Langkah pertama. Pastikan Anda berapa pada direktori Home pada termux. Kemudian lompat ke kebelakan satu kali dengan perintah `cd ..` dan buat direktori baru bernama `usr-n` dengan perintah `mkdir usr-n`.

### Langkah Kedua

Langkah kedua. Masuk ke direktori `usr-n` dengan perintah `cd usr-n` dan download file bootsrap pacman menggunakan perintah `wget <link file>`. Kamu bisa mwndownload file bootsrap pada [link ini.](https://github.com/termux-pacman/termux-packages/releases)

### Langkah Ketiga

Langkah ketiga. Ekstrak file yang sudah di download tadi dengan perintah `unzip <nama file>`. Jika sudah di ekstrak, kemudian masukkan perintah berikut: `cat SYMLINKS.txt | awk -F "←" '{system("ln -s '"'"'"$1"'"'"' '"'"'"$2"'"'"'")}'
`


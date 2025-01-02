# Bagaimana Cara Kerja Termux?

Termux pada dasarnya aplikasi yang menjalankan baris perintah _(command line)_ dengan menggunakan **system call execve(2)** dan mengarahkan kembali input, output dan kesalahan ke layar.

<details>
    <summary>System Call Execve(2)</summary>
**execve(2)** adalah salah satu system call di Unix/Linux yang digunakan untuk mengganti program yang sedang berjalan dalam sebuah proses dengan program baru. System call ini adalah inti dari implementasi eksekusi program pada sistem operasi berbasis Unix.

Fungsi dari **execve** adalah memungkinkan sebuah proses menjalankan program baru dengan mengganti kode, data, dan konteks eksekusi yang ada dengan milik program baru. Proses yang menjalankan execve tidak membuat proses baru, tetapi mengubah proses yang ada menjadi program yang diminta.

**Contoh:**

Berikut cara **execve** bekerja dalam skenario nyata di Termux menjalankan python.

Saat Anda menjalankan python di Termux:

`$ python`

1. Shell membaca input.

2. Shell menggunakan `$PATH` untuk menemukan `/data/data/com.termux/files/usr/bin/python`.

3. Shell memanggil **execve** untuk mengganti proses dengan interpreter Python. Shell akan memanggil `execve("/data/data/com.termux/files/usr/bin/python", args, envp)` untuk menjalankan perintah `python`.
</details>

Termux bukanlah mesin virtual atau jenis lain dari lingkungan yang ditiru atau disimulasikan. Semua paket yang disediakan dikompilasi silang dengan Android NDK dan hanya memiliki tambalan kompatibilitas untuk membuatnya bekerja di Android. Sistem operasi tidak menyediakan akses penuh ke sistem file-nya, sehingga Termux tidak dapat menginstal file paket ke direktori standar seperti `/ bin`, `/ etc`, `/ usr` atau `/ var`. Sebagai gantinya, semua file diinstal ke direktori aplikasi pribadi yang berlokasi di `/data/data/com.termux/files/usr`
Kami menyebutnya direktori **prefix** dan biasanya menyebutnya sebagai `$PREFIX`, yang juga merupakan variabel lingkungan yang diekspor dalam shell Termux. Perhatikan bahwa direktori ini tidak dapat diubah atau dipindahkan ke SD-Card karena:

- Sistem file harus memiliki dukungan untuk izin unix dan file khusus seperti symlink atau soket.

- Jalur **prefix** dikodekan ke semua binari.
  Selain **prefix**, pengguna dapat menyimpan file di direktori home (atau `$HOME`) yang tersedia di `/data/data/com.termux/files/home`

Namun, sistem file bukan satu-satunya perbedaan dari distribusi Linux tradisional.

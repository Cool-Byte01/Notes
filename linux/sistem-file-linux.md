# File Sistem Linux

`On a Unix system, everithing is file; if something is not a file, it is a proses.`

Pernyataan diatas mengatakan, bahwa dalam sistem UNIX _(juga berlaku unuk linux)_ semua adalah file, kalaupun ada yang bukan merupakan file, maka itu sebuah proses.

| Simbol | Jenis File   |
| ------ | ------------ |
| -      | Regular file |
| d      | Directory    |
| l      | Link         |
| c      | Special file |
| s      | Socket       |
| p      | Name pipe    |
| b      | Block device |

#### Penjelasan

- **Regular file** : merujuk pada jenis file yang berisi data atau konten yang dapat dibaca dan ditulis, seperti teks, gambar dan file biner.

- **Directory** : adalah file yang berisi file lain atau file yang memiliki daftar file lain.

- **Link** : file yang memiliki hubungan _(link)_ dengan file atau direktori lain.

- **Special File** : file yang digunakan untuk pekerjaan input dan output pada sistem linux.

- **Socket** : file yang digunakan oleh Socket TCP/IP, file ini bertugas unuk menangani pekerjaan atau proses yang berhubungan dengan jaringan.

- **Name Pipe** : file yang menyediakan komunikasi antara satu proses dengan proses lainnya.

- **Block Device** : File block device memungkinkan sistem operasi berinteraksi dengan penyimpanan seperti hardisk dan SSD.

```plaintext
$ ls –l /home/alundra
total 1148
drwx------. 4 alundra alundra 4096 Mar 17 19:55 .
drwxr-xr-x. 4 root root 32 Mar 17 19:44 ..
drwxrwxr-x. 4 alundra alundra 4096 Mar 17 19:54 data
-rw-rw-r--. 1 alundra admin 1024966 Mar 10 17:41 dokumen.kita.pptx
-rw-rw-r--. 1 alundra admin 117063 Sep 30 19:14 pengenalan.linux.docx
drwxrwxr-x. 3 alundra alundra 29 Mar 17 19:55 tugas
lrwxrwxrwx. 1 alundra alundra 9 Mar 17 19:49 uji -> /tmp/ping
```

> Perhatikanlah susunan file-file dalam sebuah
> sistem Linux di atas, perhatikanlah karakter
> awal dari setiap file yang ada.

Setiap file pada sistem Linux juga memiliki hak kepemilikan dan hak `akses read (r), write (w)` dan `execute (x)`.

### Partisi Linux

Sistem Linux tidak menggunakan istilah **Disk 0**, **Disk 1** dan seterusnya. Sistem Linux akan menamakan hard disk-nya dengan nama **_hda_** untuk hard disk pertama, **_hdb_** untuk hard disk kedua, **_hdc_** untuk hard disk ketiga dan seterusnya. Untuk hard disk SATA dan SCSI akan dinamakan **_sda_**, **_sdb_**, **_sdc_** dan seterusnya. Pada Linux, partisi file (partisi disk) adalah pembagian ruang penyimpanan pada perangkat penyimpanan seperti hard disk atau solid-state drive (SSD) menjadi beberapa bagian yang terpisah. Tujuannya adalah:

1. Mengorganisir data dengan lebih baik.
2. Meningkatkan kinerja sistem.
3. Mengurangi risiko kehilangan data.
4. Membuat pengelolaan ruang penyimpanan lebih mudah.
5. Mendukung multi-boot (menginstal beberapa sistem operasi).

#### Tabel Penamaan Hard Disk

| Penamaan | Keterangan             |
| -------- | ---------------------- |
| hda      | Hard disk IDE pertama  |
| hdb      | Hard disk IDE kedua    |
| hdc      | Hard disk IDE ketiga   |
| sda      | Hard disk SATA pertama |
| sdb      | Hard disk SATA kedua   |
| sdc      | Hard disk SATA ketiga  |

#### Tabel Penamaan Partisi Hard Disk

| Penamaan | Keterangan                                  |
| -------- | ------------------------------------------- |
| hda1     | Partisi pertama pada hard disk IDE pertama  |
| hda2     | Partisi kedua pada hard disk IDE pertama    |
| hdb1     | Partisi pertama pada hard disk IDE kedua    |
| hdb2     | Partisi kedua pada hard disk IDE kedua      |
| sda1     | Partisi pertama pada hard disk SATA pertama |
| sda2     | Partisi kedua pada hard disk SATA pertama   |
| sdb1     | Partisi pertama pada hard disk SATA kedua   |
| sdb2     | Partisi kedua pada hard disk SATA kedua     |

Ilustrasi berikut memperlihatkan sebuah linux dengan dua hardis yang sudah dipartisi menjadi beberapa bagian:

```
                sda
  +----------------------------------+
  | sda1     | sda2      | sda3      |
  +----------------------------------+

                sdb
  +----------------------------------+
  |             sdb1                 |
  +----------------------------------+


```

Pada linux ada 2 jenis partisi, yaitu:

- **Data Partition** : partisi ini digunakan untuk menyimpan program, data maupun konfigurasi yang digunakan untuk menjalankan sistem.
- **Swap Partition** : partisi yang digunakan sebagai memori tambahan untuk membantu kinerja RAM.

```
  +---------------------------------+
  | Data partition | Swap partition |
  +---------------------------------+
Linux dengan satu partisi data dan satu partisi swap.
```

Untuk membangun sistem Linux, dibutuhkan minimal satu data
partition, dan satu swap partition.

#### Tipe File Sistem

Sistem file dalam sistem operasi berguna untuk mengatur lokasi penyimpanan, menentukan besar maksimum dari suatu file dan partisi, mengatur data supaya tidak rusak sampai dengan mengatur kecepatan akses data. Terdapat berbagai macam tipe dari sistem file (file system) seperti `FAT, FAT32, NTFS, Ext2, Ext3, Ext4` dan lain-lain. Saat ini linux terbaru sudah menggunakan extended4 dan ada juga yang menggunakan **xfs**.

Adapun karakteristik sistem file `Ext4` adalah sebagai berikut:

- `Ext4` merupakan generasi keempat dari sistem file extended

- Mendukung satu file yang berukuran besar.

- Mendukung penerapan sistem file yang besar.

- Maximum individual file yang didukung adalah 16GB -16TB.

- Ukuran maximum file sistem `ext4` adalah 16EB(_extra byte_). `1EB = 1024PB(peta byte) 1PB = 1024TB(tera byte).`

- `Ext4` dapat menampung 64.000 sub-direktori.

- Dapat melakukan mounting terhadap `ext3`.

- Memiliki beberapa fitur baru, seperti multiblock allocation, delayed allocation, jurnal checksum, fast fsck dan lain-lain.

> [!NOTE]
>
> - **Multiblock Allocation**: memungkinkan file sistem untuk mengalokasikan beberapa block sekaligus untuk sebuah file dalam operasi.
> - **Delayed Allocation**: menunda pemesanan ruang di disk sampai data benar-benar ditulis.
> - **Jurnal Checksum**: mengecek catatan aktivitas disk(_jurnal_) untuk memastikan semuanya aman.
> - **Fast Fsck**: kalau ada kerusakan atau error, pemeriksaan sistem file(_fsck_) `ext4` lebih cepat, efisien dan lebih aman untuk menyimpan data. Intinya semua fitur-fitur

Contoh partisi hardisk dengan file sisem ext4:

```
                sda
  +--------------------------------------------+
  | sda1                     | sda2            |
  | Data Partition,          | Swap Partition  |
  | type : ext4              | type : ext4     |
  +--------------------------------------------+

```

#### Mount Point

**Mount point** adalah sebuah lokasi direktori dalam sistem file linux tempat sebuah perangkat penyimpanan diakses. Contoh mount point partisi **_sda1_** langsung dimount ke direktori boot, **_sda2_** ke direktori root dan seterusnya.

```
  +------------------------------------+
  | sda1   | sda2    | sda3   | sda4   |
  +------------------------------------+
      |        |        |        |
    /boot      /      /home     swap

```

> [!NOTE] > **Mounting** adalah proses menghubungkan perangkat penyimpanan atau partisi ke sistem file dengan menetapkannya ke `mount point.` Setelah `di-mount,` isi perangkat tersebut dapat diakses melalui direktori `mount point`. Sedangkan **Unmounting** adalah proses melepaskan perangkat penyimpanan dari sistem file, _(kebalikan dari proses `mounting`)_.

### Struktur File Sistem

Pada linux struktur file dan direktori disusun dalam bentuk hiarki(satu direktori tertinggi membawahi file atau direktori lain).

```
/ (Root Directory) : Direktori utama yang menjadi akar dari seluruh hirarki file sistem.
|
|-- /bin        : Berisi binary file eksekusi dasar, seperti `ls`, `cp`, `mkdir`.
|-- /boot       : File yang diperlukan untuk proses booting, seperti kernel dan GRUB.
|-- /dev        : Berisi file perangkat (device files), seperti `sda`, `tty`, `null`.
|-- /etc        : File konfigurasi sistem, seperti `passwd`, `hosts`, `fstab`.
|-- /home       : Direktori home untuk user, seperti `/home/user1`, `/home/user2`.
|-- /lib        : Library sistem yang dibutuhkan oleh `/bin` dan `/sbin`.
|-- /media      : Mount point untuk media removable (CD-ROM, USB).
|-- /mnt        : Mount point sementara untuk file sistem tambahan.
|-- /opt        : Aplikasi tambahan yang diinstal secara manual.
|-- /proc       : Informasi kernel dan proses yang berjalan (virtual filesystem).
|-- /root       : Direktori home untuk user `root` (superuser).
|-- /run        : Data runtime dari sistem (seperti socket dan PID files).
|-- /sbin       : Binary file eksekusi sistem untuk administrator, seperti `fsck`, `ifconfig`.
|-- /srv        : Data yang disediakan oleh server, seperti web server atau FTP.
|-- /sys        : Informasi tentang perangkat keras dan kernel (virtual filesystem).
|-- /tmp        : Direktori untuk file sementara yang dapat dihapus otomatis.
|-- /usr        : Aplikasi dan file yang dibagikan untuk user.
|   |-- /usr/bin     : Binary file untuk aplikasi user.
|   |-- /usr/sbin    : Binary file untuk administrator.
|   |-- /usr/lib     : Library tambahan untuk `/usr/bin` dan `/usr/sbin`.
|   |-- /usr/local   : Aplikasi yang diinstal secara lokal oleh admin.
|
|-- /var        : Data yang berubah secara dinamis.
|   |-- /var/log     : Log file sistem, seperti `syslog`, `auth.log`.
|   |-- /var/tmp     : File sementara yang bertahan lebih lama dari `/tmp`.
|   |-- /var/lib     : File database atau state aplikasi.
```

> [!WARNING]
>
> Nama file maupun direktori dalam linux bersifat **case sensitive**, yang berarti huruf kecil dan besar akan memiliki makna yang berbeda.

### Absolute dan Relative Pathname

- **Absolute Pathname**: mengakses suatu direktori atau file yang dimulai dari root(/) direktori. ex: `$ ls /etc` <- diawali dengan tanda /
- **Relative Pathname**: mengakses suatu direktori atau file tanpa harus mengikuti struktur hirarki file dan tidak harus diawali dengan /. ex: `cd belajar-linux/bab_1.md`

[source: E-Book Linux Fundamentals](https://repository.urindo.ac.id/files/original/392d9b097d3d33a208d88999ef72ed4c2e979dff.pdf)

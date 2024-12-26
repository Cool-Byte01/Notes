# Dasar-Dasar Linux

## Pengenalan Linux

Linux adalah sistem operasi open source berbasis unix yang dirancang untuk memberikan fleksibilitas, keamanan dan stabilitas. Linux pertama kali dikembangkan oleh Linys Torvlads pada tahun 1991. Saat ini Linux dikembangkan oleh komunitas global yang terdiri dari individu, organisasi dan juga perusahaan.

## Komponen Linux

- **Kernel** adalah bagian inti(core) dari sistem operasi yang langsung berhubungan dengan hardware. Kernel bertanggung jawab dengan tugas utama dari sistem operasi, seperti menngerakkan hardisk untuk membuat file, menulis file dan lain-lain.Kernel berfungsi sebagai jembatan antara software dan hardware.

- **System Library** merupakan sekumpulan file yang digunakan untuk mengakses fitur kernel. System library dibutuhkan karena kernel harus ditriger(dipicu) untuk melakukan pekerjaannya.

- **System Utility** merupakan komponen berupa aplikasi yang digunakan oleh user untuk melakukan pekerjaan spesifik, seperti menjalankan tugas administrasi, manajemen file, monitoring sistem dan konfigurasi jaringan. System Utility dibutuhkan karena jika hanya kernel dan library, maka tidak akan mudah bagi user untuk menggunakan dan menjalankan sistem operasi.

* **Komponen Linux**

```
+-------------------------------------------------+
|              Linux Operating System             |
+-------------------------------------------------+
|          System Softwares, User Process,        |
|         User Utility, Compilers                 |
+-------------------------------------------------+
|                  System Libraries               |
+-------------------------------------------------+
|                        Kernel                   |
+-------------------------------------------------+
|                  Kernel Modules                 |
+-------------------------------------------------+
| Hardware                                        |
| CPU               RAM                  I/O      |
+-------------------------------------------------+
```

> [!NOTE]
> **Kernel modul** adalah bagian tambahan dari kernel yang dapat dimuat atau dilepaskan _(loadable/unloadable)_ secara dinamis sesuai kebutuhan, tanpa harus memodifikasi atau memuat ulang kernel utama. Modul ini memungkinkan kernel untuk diperluas atau diubah fungsinya tanpa memengaruhi inti kernel yang sedang berjalan. Contoh: driver untuk printer, LAN card dan USB.

- **Arsitektur Linux**

```
+-------------------------------------------------+
|                     User 1                      |
|            Applications, Compilers              |
+-------------------------------------------------+
|                      Shell                      |
+-------------------------------------------------+
|                     Kernel                      |
+-------------------------------------------------+
|                     Hardware                    |
+-------------------------------------------------+
```

### Hubungan Kerja Ketiganya

1. **Aplikasi** mengirimkan permintaan ke **system library**
2. **System library** menerjemahkan permintaan menjadi **sistem panggilan** _(system call)_ ke kernel.
3. **Kernel** menangani permintaan dan mengatur hardware atau sumber daya sistem.
4. Hasilnya dikembalikan melalui jalur yang sama, memungkinkan aplikasi dan user untuk menerima hasil dari operasi tersebut.

Dengan kata lain:

- **Kernel** : Mengatur atau mengelola hardware.
- **System Library** : Menjadi perantara antara aplikasi dan kernel.
- **System Utility** : Alat bagi user untuk berinteraksi dengan sistem operasi.

## Fitur Dasar Linux

Fitur-fitur utama yang dimiliki oleh linux adalah sebagai berikut:

- **Portable(Multi-Platfrom)** : Linux dan program-program pendukungnya dapat diinstall dan berjalan pada berbagai hardware.

- **Open Source** : Source code linux dapat diambil dan digunakan secara gratis.

- **Multi-User** : Beberapa user dapat menggunakan linux dan resource sistem pada saat bersamaan.

- **Multiprogramming** : Linux dapat menjalankan beberapa aplikasi sekaligus.

- **Hierarchial File System** : Struktur file sistem dan user disusun seperti pohon _(tree structure)_. Dengan direktori **root** _(/)_ sebagai titik awal.

- **Shell** : Adalah interpreter program _(penterjemah)_ bagi user untuk menjalankan perintah linux.

- **Scurity** : Linux menyediakan fitur scurity _(keamanan)_ bagi user, baik itu berupa password, kontrol akses terhadap file maupun fitur enkripsi terhadap file.

## Distribusi Linux

Distribusi Linux atau yang biasa disebut `distro linux` adalah sistem operasi yang dibangun dari kernel linux dan aplikasi dari sistem manajemen, ciri khususnya adalah utility GNU. Semua linux memiliki kernel yang sama yaitu kernel linux yang dibuat oleh Linus Trodvalds, tetapi biasanya setiap distro linux memiliki fitur yang berbeda. Distro linux dapat dikategorikan menjadi tiga kategori, yaitu:

1. **Enterprise** : Distro enterprise dirancang untuk keperluan bisnis dan perusahaan. Fokusnya adalah pada stabilitas, keamanan, dan dukungan jangka panjang (LTS). Biasanya, distro ini didukung oleh tim pengembang profesional dan sering kali menyediakan layanan dukungan teknis.

	- Karakteristik: Stabil, reliabel, memiliki dukungan komersial.

	- Contoh: Red Hat Enterprise Linux (RHEL), SUSE Linux Enterprise Server (SLES), Oracle Linux.

	- Penggunaan: Server perusahaan, data center, cloud computing.


2. **Desktop** : Distro desktop dirancang untuk pengguna sehari-hari, baik untuk kebutuhan pribadi maupun pekerjaan ringan. Fokusnya adalah pada kemudahan penggunaan, antarmuka yang ramah pengguna, dan dukungan terhadap perangkat keras yang umum digunakan.

	- Karakteristik: Mudah digunakan, fokus pada GUI (Graphical User Interface), cocok untuk pengguna pemula hingga tingkat lanjut.

	- Contoh: Ubuntu, Linux Mint, Fedora Workstation, Elementary OS.

	- Penggunaan: Pengguna umum, pelajar, pengembang software.

3. **Special Purpose** : Distro ini dirancang untuk tugas-tugas spesifik atau kebutuhan tertentu. Biasanya, ukurannya kecil dan hanya memiliki perangkat lunak yang relevan dengan tujuannya.

	- Karakteristik: Dioptimalkan untuk tugas tertentu (misalnya keamanan, edukasi, atau recovery).

	- Contoh:

		1. Keamanan: Kali Linux, Parrot OS (pentesting dan keamanan siber).

		2. Edukasi: Edubuntu, Sugar on a Stick.

		3. Recovery: SystemRescue, Clonezilla Live.

		4. Embedded/IoT: OpenWRT, Yocto.


	- Penggunaan: Forensik digital, pengetesan keamanan, pengembangan IoT, atau administrasi jaringan.


# [M1] Dasar Virtualisasi Linux Server dan Basic File System Management

## I. Tujuan Praktikum

- I.1 Praktikan mampu memahami teori umum tentang sistem operasi.
- I.2 Praktikan mampu memahami hierarki direktori dan perintah-perintah dasar yang ada pada Linux.
- I.3 Praktikan dapat melakukan instalasi sistem operasi Rocky Linux 8.6.
- I.4 Praktikan mampu melakukan pembuatan file dan user management pada sistem operasi Rocky Linux 8.6.
- I.5 Praktikan mampu memahami proses Operating System.
- I.6 Praktikan mampu memahami pengertian, penggunaan, serta pemanfaatan Text Editor.
- I.7 Praktikan mampu mengoperasikan Text Editor.

## II. Alat dan Bahan

- 2.1 PC/Laptop
- 2.2 ISO Rocky Linux 8.6
- 2.3 VMWare Workstation 16.x

## III. Landasan Teori

### 3.1 Sistem Operasi

#### 3.1.1 Pengertian

Operating System (OS) atau sistem operasi adalah salah satu perangkat lunak atau software yang bertanggung jawab mengatur atau mengontrol kerja perangkat keras atau hardware dan menjalankan aplikasi atau software di dalam suatu sistem komputer.

Dengan kata lain sistem operasi adalah sistem yang mengendalikan operasi dasar dan memastikan sistem dalam komputer dapat berjalan dengan semestinya. Sistem operasi memungkinkan suatu aplikasi dapat berfungsi sehingga sistem operasi juga disebut sebagai *essential component*. Komputer dan sistemnya hanya dapat berfungsi dengan adanya sistem operasi kecuali jika komputer sedang dalam keadaan booting.

Fungsi-fungsi dari sistem operasi yaitu:

1. Menjalankan operasi dasar.
2. Mengatur kerja hardware dan software.
3. Wadah program atau aplikasi.
4. Menyajikan tampilan.
5. Mengkoordinasi kerja perangkat komputer.
6. Mengoptimalkan fungsi perangkat komputer.
7. Mengawasi dan melindungi jalannya suatu fungsi program.

Bagian-bagian dari sistem operasi secara umum yaitu:

1. **Mekanisme Boot**, meletakkan kernel ke dalam memory kernel.
2. **Kernel**, inti dari sebuah sistem operasi.
3. **Command Interpreter atau shell**, membaca input berupa perintah dan menyediakan beberapa fungsi standar dan fungsi dasar yang dapat dipanggil oleh aplikasi/program maupun perangkat lunak lain.
4. **Driver**, berinteraksi dengan hardware sekaligus mengontrol kinerja hardware.
5. **Resource Allocator**, sistem operasi bertugas mengatur dan mengalokasikan sumber daya dari perangkat.
6. **Handler**, mengendalikan sistem perangkat agar terhindar dari kekeliruan (error) dan penggunaan sumber daya yang tidak perlu.

#### 3.1.2 Macam-macam OS

Adapun beberapa macam OS yang perlu diketahui, antara lain:

**A. UNIX**

UNIX adalah sebuah sistem operasi komputer yang diawali dari Project Multics (Multiplexed Information and Computing Service) pada tahun 1965 yang dilakukan American Telephone and Telegraph AT&T, General Electric (GE), dan Institut Teknologi Massachusetts, dengan biaya dari Departemen Pertahanan Amerika (Department of Defence Advanced Research Project, DARPA atau ARPA), UNIX didesain sebagai sistem operasi yang portable, multi-tasking dan multi-user.

Arsitektur UNIX dan model client-server merupakan salah satu elemen yang paling penting dalam perkembangan internet dan membuat proses komputasi berubah menjadi terpusat di dalam jaringan daripada proses tunggal di komputer.

Terdapat beberapa sistem operasi yang berbasis UNIX yaitu, Ubuntu, Debian, Solaris, FreeBSD, Linux Mint, OpenSuse, Zenwalk Linux, Kali Linux, Garuda OS, BlankOn, IGOS Nusantara, dan lain-lain.

**B. Linux**

Linux merupakan salah satu operating system (OS), sama seperti Windows atau sistem operasi lainnya. Linux merupakan sistem operasi yang open source, artinya dengan Linux kita bisa melihat source code miliknya, bisa dilakukan modifikasi, dan bisa dikembangkan oleh siapa saja. Linux bermula dari proses pengembangan UNIX yang ingin melakukan implementasi bebas dari POSIX, multi-tasking, virtual memory, shared libraries, demand loading, proper memory management, dan multi user.

Saat ini Linux adalah sistem UNIX yang paling lengkap karena bisa digunakan untuk jaringan, pengembangan software, dan bahkan untuk pekerjaan sehari-hari. Saat ini Linux merupakan alternatif sistem operasi yang jauh lebih murah jika dibandingkan dengan sistem operasi komersial.

Distro Linux merupakan OS yang dikembangkan berdasarkan kernel Linux yang sudah dimodifikasi dan dikembangkan. Saat ini banyak yang mencoba untuk mengembangkan Linux, salah satunya yaitu Rocky Linux. Rocky Linux merupakan OS open source dan dikembangkan oleh Rocky Enterprise Software Foundation. Sampai saat ini Rocky juga memiliki dokumentasi dan komunitas yang aktif.

Berikut terdapat kelebihan dan kekurangan pada Linux, yaitu:

a. Kelebihan

1. Linux merupakan open-source yang berarti OS ini terbuka untuk siapa saja.
2. Linux membutuhkan authorization setiap kali user ingin menjalankan program. Keamanan privacy dan data personal pengguna juga terjamin di Linux.
3. Linux lebih ringan karena Linux lebih ke command line melalui perintah yang berbasis text.
4. User memiliki kebebasan untuk memodifikasi OS dengan sendirinya.
5. Mempunyai banyak distro yang terus aktif dan berkembang.

b. Kekurangan

1. Linux tidak banyak mendukung aplikasi. Seperti aplikasi pengeditan video, gambar, desain, dan sebagainya.
2. Jika mengalami kendala, Linux hanya memiliki layanan support yang berbayar.
3. Tidak semua hardware akan otomatis terdeteksi oleh Linux.

**C. CentOS**

CentOS adalah sistem operasi yang didasari oleh Red Hat Enterprise Linux (RHEL). Kepanjangan dari sistem operasi CentOS yaitu Community Enterprise Operating System, sistem operasi ini merupakan salah satu distribusi Linux open source sebagai bentuk usaha dalam penyediaan platform komputasi berkelas enterprise, yang memiliki sepenuhnya kompatibilitas kode biner dengan kode sumber yang menjadi induknya, yang sumbernya berasal dari Red Hat Enterprise Linux (RHEL).

CentOS mulai aktif dikembangkan oleh sekelompok tim inti dan didukung oleh komunitas pengguna skala perusahaan, administrator jaringan, administrator sistem dan para pengguna Linux lainnya.

Berikut terdapat kelebihan dan kekurangan pada CentOS, yaitu:

a. Kelebihan

1. Sistem operasi freeware (gratis) yang cocok untuk perusahaan.
2. Satu-satunya sistem operasi freeware yang didukung resmi oleh Cpanel.
3. Banyak dukungan komersial yang diberikan vendor.
4. Kompatibel dengan driver RHEL (Red Hat Enterprise Linux).
5. Bagus digunakan dalam jangka panjang karena mendapat support update dari beberapa developer.

b. Kekurangan

1. Tergantung pada distro Red Hat.
2. Susah digunakan oleh pemula.
3. Tampilan website resmi CentOS kurang menarik.
4. Kurangnya dokumentasi mengenai CentOS.

#### 3.1.3 User Interface

User interface merupakan bentuk tampilan grafis yang berhubungan langsung dengan pengguna. Interface berfungsi untuk menghubungkan antara pengguna dengan sistem operasi, sehingga komputer tersebut bisa digunakan.

**A. GUI**

GUI atau Graphical User Interfaces adalah suatu sistem yang membuat para pengguna atau user mampu berinteraksi dengan suatu perangkat komputer yang digunakan oleh user tersebut. GUI sendiri dapat dikendalikan menggunakan beberapa macam alat input, seperti mouse, keyboard, touchscreen, dan lain sebagainya. Sistem Operasi GUI secara umum terdapat fitur jendela, menu, tombol, ikon, dan lainnya yang didesain supaya penggunanya lebih mudah dalam berinteraksi dengan sistem operasi atau aplikasi.

Sedangkan dalam penerapan GUI lebih banyak digunakan untuk kebutuhan pengguna umum, karena tujuannya lebih ke User Friendly.

Berikut terdapat kelebihan dan kekurangan GUI, yaitu:

a. Kelebihan

1. Desain menarik dan mudah digunakan.
2. Tidak perlu mengingat baris dan perintah.

b. Kekurangan

1. Membutuhkan spesifikasi hardware yang besar.
2. Perintah tersembunyi harus dicari menggunakan bantuan (help).
3. Performa kinerja perangkat jauh lebih berat.

**B. CLI**

Command Line Interface atau lebih akrab dikenal CLI adalah sistem user interface berupa teks program untuk menjalankan perintah komputer. Sistem operasi yang mengimplementasikan CLI dalam shell untuk akses interaktif ke fungsi atau layanan sistem operasi. Dalam berinteraksi antara pengguna dengan sistem operasi hanya bisa dilihat seperti sebuah baris kata-kata saja dan untuk melakukan interaksi tersebut dapat menggunakan keyboard dengan cara mengetikkan perintah (command) tertentu.

Command Line Interface sering diterapkan pada perangkat terminal yang juga mampu menghandle text user interface yang menggunakan kursor untuk menempatkan simbol pada layar tampilan. Program dengan Command Line Interface (CLI) umumnya lebih mudah untuk diotomatisasi melalui script. CLI juga dikenal lebih ringan dalam pengoperasiannya dibandingkan GUI. Contoh sistem operasi berbasis CLI adalah DOS, Unix, Debian, CentOS, Ubuntu, Mikrotik, Cisco IOS, dan sebagainya.

Berikut terdapat kelebihan dan kekurangan CLI, yaitu:

a. Kelebihan CLI:

1. Performa lebih tinggi.
2. Lebih efisien dalam penggunaan.
3. Bisa berjalan dengan baik di komputer spesifikasi rendah.
4. Bersifat open source dan dapat dikembangkan secara gratis.

b. Kekurangan CLI:

1. Kurang menarik bagi pemula.
2. Harus mengingat perintah yang digunakan dalam sistem operasi CLI karena kesalahan penulisan bisa menyebabkan error pada perintah programnya.

### 3.2 ISO File

#### 3.2.1 Pengertian

ISO File merupakan sebuah format file yang dapat menampung data dalam bentuk gambaran dari CD/DVD serta bisa disimpan dalam bentuk digital. File ISO disebut juga dengan istilah CD/DVD image, karena file ISO bisa disebut sebagai pengganti dari kepingan CD/DVD yang dimana untuk membukanya membutuhkan sebuah software khusus yang terinstal pada komputer.

File ISO (International Organization for Standardization) adalah jenis file arsip yang memungkinkan pengguna untuk menyalin isi dari seluruh drive atau disk. File jenis ISO tidak dikompres dan mengandung banyak file lain yang semuanya telah dikumpulkan bersama-sama untuk transfer cepat dan mudah. File ISO yang paling sering digunakan sebagai pengganti CD tapi juga dapat digunakan untuk menyalin server, hardisk, atau perangkat penyimpanan lainnya. Perangkat lunak ISO memungkinkan pengguna untuk membuat file ISO serta mengekstraknya.

#### 3.2.2 Tujuan

Tujuan dari penggunaan File ISO yaitu untuk mempermudah pendistribusian atau melakukan pengarsipan suatu CD/DVD tanpa harus menggunakan CD/DVD secara fisik. Selain itu file ISO ini juga mempermudah pengguna dalam menggunakan file CD/DVD dengan CD/DVD virtual tanpa harus menggunakan CD/DVD drive.

#### 3.2.3 Fungsi

Dibawah ini merupakan fungsi-fungsi yang terdapat dalam penggunaan yaitu:

1. Backup data menjadi lebih mudah.
2. Sebagai pengganti CD/DVD.
3. Mengurangi resiko kerusakan.
4. Menjaga keamanan data.

### 3.3 VMWare Workstation

VMWare Workstation adalah suatu perangkat lunak yang dapat menciptakan atau mensimulasikan PC baru, yang disebut mesin virtual. Perangkat keras yang terdapat di dalam mesin virtual sama seperti perangkat keras yang dipakai PC, misalnya CPU, RAM, hardisk, keyboard, mouse, CD/DVD ROM, soundcard, kata lain PC di dalam PC.

VMware dapat digunakan untuk membuat virtualisasi server, komputer, sistem operasi, storage device, aplikasi, networks, dsb. Jadi, bisa diluruskan bahwa dengan VMWare, bisa membuat komputer virtual di dalam komputer fisik, serta menjalankan sistem operasi di dalam sistem operasi lainnya.

Berikut adalah cara kerja VMWare:

1. VMWare bekerja dengan membuat layer hardware virtual (virtual machine) pada komputer pengguna (physical machine).
2. VMWare akan membuat storage virtual, CPU virtual, RAM virtual, DVD ROM virtual, dan berbagai komponen virtual lainnya untuk kemudian menjadi virtual machine yang utuh.
3. Layer software yang disebut dengan hypervisor yang secara dinamis mengalokasikan resource di komputer fisik (host computer) ke virtual machine sesuai dengan yang dibutuhkan.
4. Begitu virtual machine tersebut di-install sistem operasi, maka sistem operasi di virtual machine tersebut (guest OS) akan berjalan terisolasi di sistem operasi utama (host OS).
5. Setiap state dari virtual machine tersebut bakal tersimpan dalam bentuk file yang nantinya bisa digandakan dan dipindahkan dengan mudah.
6. Dengan demikian pengguna bisa menjalankan beberapa virtual machine dengan beberapa spesifikasi dan sistem operasi hanya dari satu komputer fisik.

### 3.4 Terminal

Terminal merupakan sebuah bentuk command prompt, terminal bisa membantu dalam mengontrol file, membuat folder, membuat akses, merubah akses ataupun membaca, membuat, merubah file, dan fungsi lainnya. Kegunaan dari terminal yaitu sebagai peramban berkas. Kita dapat menggunakan terminal sebagai peramban berkas yaitu untuk menempatkan berkas dan juga untuk membatalkan perubahan yang telah dibuat.

### 3.5 File System

File System merupakan salah satu metode penyimpanan dan metode yang bisa mengorganisir data atau file pada komputer. Pada file system tersedia aturan dan tata cara penyimpanan data dan program yang dimiliki oleh sebuah sistem operasi serta seluruh user dari sistem komputer tersebut. Beberapa contoh file system yaitu, FAT (FAT16 dan FAT32), NTFS adalah singkatan dari New Technology File System, ZFS, EXT2, dan lain-lain.

### 3.6 Hierarki Direktori

System file di Linux dan UNIX diorganisasikan secara hierarki, seperti struktur pohon. Level tertinggi dari file system adalah direktori root atau (`/`). Semua file dan direktori yang lain berada di bawah direktori root.

Sebagai contoh: `/home/sisjar/sisop.odt` menunjukkan path lengkap ke file `sisop.odt` yang berada di direktori `sisjar`, yang juga berada di bawah direktori `home`, dan semuanya berada di bawah direktori root (`/`).

Di bawah direktori root (`/`) sejumlah direktori-direktori penting bersama-sama membentuk distribusi Linux:

**Tabel 3.6 Tabel Hierarki Direktori**

| Nama Direktori | Fungsi Direktori |
|---|---|
| `/` (root) | Root merupakan puncak dari seluruh direktori dari system Linux. |
| `/bin` | Direktori /bin berisi perintah dasar yang dibutuhkan oleh root (superuser) maupun user. Sebagian perintah dasar yang bisa anda jalankan disimpan dalam direktori ini. |
| `/boot` | Direktori /boot berisi file-file boot loader diantaranya grub atau lilo dan program yang dijalankan saat proses booting. Kernel, initrd dan system.map juga terletak di dalam /boot. |
| `/dev` | Direktori /dev sebenarnya bukan berisi file melainkan perangkat-perangkat yang terdapat pada system yang kemudian dikenal system dengan sebuah file-file. |
| `/etc` | Direktori /etc berisi file-file konfigurasi dan layanan yang dijalankan sistem. |
| `/home` | Direktori /home merupakan tempat menyimpan data yang dikerjakan user. Setiap user yang terdaftar secara otomatis akan dibuatkan direktori khusus untuknya di /home. |
| `/lib` | Direktori /lib berisi file-file library atau pustaka dari semua aplikasi binary yang tersimpan dalam direktori /sbin dan /bin. |
| `/lost+found` | Direktori /lost+found menyimpan file-file yang berhasil dipulihkan saat sistem crash. Dengan melihat ke dalam /lost+found mungkin kita dapat menemukan file yang hilang. |
| `/media` | Direktori /media berisi direktori-direktori mount point (misal partisi harddisk, flash disk, DVD) yang telah ditingkatkan. |
| `/sbin` | Direktori /sbin berisi file-file biner yang esensinya untuk sistem dan mengendalikan sistem. File-file biner dianggap sebagai aplikasi sistem ini, jika dioperasikan secara tidak tepat bisa berpotensi merusak. Biasanya aplikasi yang ada hanya bisa dijalankan oleh administrator atau root. |
| `/root` | Direktori /root merupakan home direktori dari user root (superuser). |
| `/opt` | Direktori /opt berisi paket aplikasi tambahan yang kita install ke dalam system. Namun saat ini /opt jarang digunakan dikarenakan beberapa paket software terpisah menggunakan direktori untuk menyimpan paket yang menuju ke lokasi manapun. |
| `/proc` | Direktori /proc merupakan direktori yang hampir sama dengan /dev namun /proc berkaitan dengan system yang sedang menjalankan proses. |
| `/tmp` | Direktori /tmp berisi file temporer. Beberapa distro akan otomatis membersihkan isi dari /tmp sewaktu reboot. |
| `/usr` | Direktori /usr berisi program-program yang bisa diakses oleh user, program source code. Di dalam /usr hampir mirip dengan direktori /bin, /sbin, dan /lib. |
| `/var` | Direktori /var digunakan untuk menyimpan informasi proses, seperti system history, access logs, dan error logs. Direktori /var merupakan direktori yang isinya sangat dinamis jika digunakan di dalam server. Sangat dianjurkan /var ini untuk diletakkan di partisi terpisah karena direktori /var dapat membengkak dengan sangat cepat. |
| `/srv` | Direktori ini berisi data untuk semua layanan sistem yang bersangkutan. Biasanya nama layanan dituliskan sebagai subdirektori. |

### 3.7 File Management dan Perintah Dasar

#### 3.7.1 Substitusi User

Superuser (`su`) adalah user tertinggi atau user root yang ada pada sistem operasi seperti sistem Unix. Di dalam superuser ini kita dapat melakukan apa saja karena tidak ada pembatasan. Perintah `su` dapat digunakan untuk berpindah dari user biasa ke user root, dan juga dapat digunakan untuk berpindah dari user root ke user lainnya juga.

Untuk mendapatkan akses root dengan menggunakan user lain yang tidak memiliki akses root, pada terminal Rocky Linux dapat mengetikkan command `su` lalu enter, lalu masukkan password dari root-nya, lalu tekan enter. Jika tanda `$` sudah berubah menjadi tanda `#` (yang mana menandakan anda sedang berada di user root) maka sudah berhasil berpindah dari user biasa ke user root.

Untuk dapat berpindah dari user root ke user biasa atau user lain, kita dapat menggunakan perintah yang sama, yaitu `su` lalu diikuti oleh nama usernya, lalu tekan enter. Jika tanda `#` sudah berubah menjadi tanda `$` maka Anda sudah berhasil berpindah user.

#### 3.7.2 Perintah-Perintah Dasar

Berikut perintah dasar pada Rocky Linux beserta fungsinya:

**Tabel 3.7.2.1 Tabel Perintah Dasar**

| Command | Fungsi |
|---|---|
| `man` | Menampilkan opsi yang ada pada penggunaan suatu perintah. |
| `pwd` | Mengetahui posisi direktori dimana saat itu user berada. |
| `cal` | Menampilkan kalender. |
| `date` | Menampilkan hari. |
| `ls` | Menampilkan list data pada suatu direktori. |
| `cd` | Pindah direktori. |
| `mkdir` | Membuat direktori baru. |
| `touch` | Membuat file. |
| `cat` | Membaca isi file. |
| `rm` | Menghapus file. |
| `rmdir` | Menghapus direktori. |
| `cp` | Menyalin file atau direktori. |
| `mv` | Memindahkan file atau direktori. |
| `chmod` | Memberikan atau mengubah hak akses suatu file atau direktori. |
| `yum` | Install sesuatu melalui cloud atau internet. |
| `whoami` | Melihat user yang digunakan saat ini. |
| `su` | Login sebagai user lain. |
| `exit` | Logout sebagai user lain. |
| `find` | Mencari lokasi suatu file berada. |

Berikut ini adalah struktur perintah yang umum digunakan:

1. Melihat opsi pada suatu perintah.

```bash
#man [nama perintah]
```

Contoh:

```bash
#man su
```

2. Mengetahui posisi direktori yang sedang digunakan.

```bash
#pwd
```

3. Melihat kalender pada bulan dan tahun secara spesifik.

```bash
#cal [bulan] [tahun]
```

Contoh:

```bash
#cal 11 2021
```

4. Melihat hari tanggal saat itu.

```bash
#date
```

5. Melihat seluruh isi suatu direktori.

```bash
#ls [path direktori tujuan]
```

Contoh:

```bash
#ls /home
```

6. Pindah Direktori.

```bash
#cd [path direktori utama]
```

Contoh:

```bash
#cd modulsatu
```

7. Membuat direktori.

```bash
#mkdir [path_direktori/nama_direktori_baru]
```

Contoh:

```bash
#mkdir modulsatu
```

8. Membuat file.

```bash
#touch [path_direktori/nama_file_baru]
```

Contoh:

```bash
#touch Tazkia.txt
```

9. Menghapus data.

```bash
#rm [nama_file atau nama_folder]
```

Contoh:

```bash
#rm Tazkia.txt
```

10. Menghapus direktori.

```bash
#rmdir [path_direktori]
```

Contoh:

```bash
#rmdir modulsatu
```

11. Menyalin data.

```bash
#cp [nama_file_asli] [nama_file_hasil]
```

Contoh:

```bash
#cp Tazkia.txt Syarah.txt
```

12. Memindahkan data.

```bash
#mv [nama_file_asli][path_destination] [nama_file_hasil]
```

Contoh:

```bash
#mv Tazkia.txt /home/modulsatu/Syarah.txt
```

13. Login ke user lain.

```bash
su [nama_user]
```

Contoh:

```bash
#su sisjar_rockylinux
```

14. Mencari lokasi suatu file.

```bash
#find ["nama_file"]
```

Contoh:

```bash
#find Tazkia.txt
```

**Mengubah atau memberikan hak akses**

Pada dasarnya terdapat 3 macam hak akses (permission) pada sistem operasi Linux yaitu sebagai berikut:

**Tabel 3.7.2.2 Macam-macam hak akses file pada Linux**

| Hak Akses (Permissions) | Notasi | Fungsi |
|---|---|---|
| Read | `r` | User lain bisa membuka serta membaca file tersebut. |
| Write | `w` | User lain bisa menulis serta memodifikasi file tersebut. |
| Execute | `x` | User lain bisa menjalankan atau mengeksekusi file tersebut. |

Selain macam-macam hak akses pada Linux, juga memiliki mode akses yang digunakan pada Linux yaitu:

**Tabel 3.7.2.3 Macam-macam mode akses file pada Linux**

| Mode Hak Akses | Notasi | Fungsi |
|---|---|---|
| Owner | `u` | Hak akses yang dimiliki oleh user file atau direktori, sehingga user lain tidak dapat melakukan modifikasi pada file atau direktori tersebut. |
| Group | `g` | Hak akses yang dimiliki oleh suatu group tempat user berada. |
| Other | `o` | Hak akses yang dimiliki setiap user selain pemilik file atau direktori. |

Penjelasan Gambar 3.7.2.1 (Mode Akses dan Hak File dalam Linux):

a. Tanda pertama merupakan tipe file atau direktori. Pada gambar terdapat tanda `d` yang menandakan suatu direktori.
b. 3 tanda berikutnya adalah `rwx` yang merupakan permission file yang dimiliki oleh owner.
c. 3 tanda berikutnya adalah `rwx` yang merupakan permission file yang dimiliki oleh group.
d. 3 tanda yang terakhir adalah `rwx` yang merupakan atribut permission file untuk other atau pengguna lain.

Untuk memasukkan mode akses tersebut ke dalam perintah maka kita gunakan mode numerik sebagai pengganti dari notasi-notasi tersebut. Notasi `r` menjadi angka 4, notasi `w` menjadi angka 2, dan notasi `x` menjadi angka 1.

Command:

```bash
#chmod u+[r,w,x],g+[r,w,x],o+[r,w,x] [path_tujuan]
```

Contoh:

```bash
#chmod u+rwx,g+rwx,o+rwx /home/sisop/sisjarlab.txt
```

atau

```bash
#chmod *** (ex:#chmod 777)
```

Untuk menampilkan hak akses pada file atau direktori, kita dapat menggunakan command `ls -l` pada terminal Rocky Linux. Command tersebut akan menampilkan list dari file dan direktori beserta dengan beberapa informasi, seperti hak aksesnya, last modified, PID, dan nama dari file atau direktori itu sendiri.

### 3.8 User Management

User Management adalah suatu mekanisme atau langkah-langkah untuk mengatur penggunaan user. Berikut merupakan materi user management yang akan diulas pada praktikum kali ini.

#### 3.8.1 Menambahkan User

Untuk menambahkan user baru pada Linux khususnya Rocky Linux, pengguna harus mengubah hak aksesnya terlebih dahulu menjadi root atau menggunakan perintah `sudo` pada awal perintah. Karena user biasa tidak diizinkan untuk menambahkan user lainnya. Menambahkan user dapat dilakukan dengan 2 cara:

1. **Adduser**

```bash
#adduser [nama_user_baru]
```

Setelah itu ketikkan command `passwd` untuk memasukkan password ke user baru.

```bash
#passwd [nama_user_baru]
```

2. **Useradd**

```bash
#useradd [nama_user_baru]
```

Setelah itu ketikkan command `passwd` untuk memasukkan password ke user baru.

```bash
#passwd [nama_user_baru]
```

#### 3.8.2 Menghapus User

Seperti halnya untuk menambahkan user, untuk menghapus sebuah user, pengguna harus mengubah hak aksesnya terlebih dahulu menjadi root atau menambahkan perintah `sudo` pada awal perintah. Berikut adalah perintah untuk menghapus user:

Userdel

```bash
#userdel -r [nama_user]
```

atau

```bash
$sudo userdel -r [nama_user]
```

Kita dapat menghapus user secara keseluruhan (file, home, dll) dengan menggunakan command di atas.

#### 3.8.3 Mengubah Password

1. Untuk mengubah password user yang sedang kita pakai, cukup dengan mengetikkan perintah:

```bash
#passwd
```

2. Namun untuk mengganti password user lain atau user yang sedang tidak kita gunakan, maka pengguna harus masuk menjadi mode root atau menambahkan perintah `sudo` di awal perintah `passwd` dan diikuti dengan nama user yang akan diganti password-nya.

```bash
#passwd [nama_user]
```

#### 3.8.4 Melihat List User yang Terdaftar

Jika sudah membuat beberapa user, maka perlu bagi pengelola atau pengguna untuk melihat user apa saja yang telah dibuat. Untuk melihat tersebut, kita tinggal membaca file `/etc/passwd`.

```bash
#cat /etc/passwd
```

### 3.9 Text Editor

#### 3.9.1 Pengertian

Text editor adalah sebuah program atau perangkat lunak yang digunakan untuk menyunting teks. Pada umumnya text editor digunakan untuk menulis baris kode, menyunting file configuration, dan masih banyak lagi. Text editor sendiri secara default ter-install pada setiap sistem operasi. Di Linux, text editor terbagi menjadi dua jenis yaitu text editor yang menggunakan Graphical User Interface (GUI) dan text editor yang menggunakan Command Line (Console/Terminal).

#### 3.9.2 Varian

**A. Nano Editor**

GNU Nano adalah sebuah text editor yang digunakan pada sistem operasi berbasis Unix, tampilan Nano editor menggunakan Command Line Interface. Nano editor merupakan tiruan dari Pico sehingga bertujuan untuk meniru fungsionalitas dan penggunaan yang mudah dari antarmuka Pico. Berbeda dengan Pico, Nano editor dilisensikan di bawah GNU General Public License (GPL) dan dirilis sebagai perangkat lunak bebas.

1. Perintah dan Cara Kerja Nano Editor

Nano editor dapat digunakan dengan mudah, sehingga user dapat langsung mengetik untuk memasukkan teks. Nano editor menggunakan tombol control sebagai cara pengoperasiannya, sehingga disebut *keyboard oriented*. Jika user kebingungan dalam penggunaan Nano editor, bisa dengan cara `Ctrl+G` maka akan dibawa menuju halaman bantuan. Untuk masuk ke dalam Nano editor dapat dilakukan dengan cara memasukkan command berikut pada terminal:

```bash
[root@localhost sisjarlab] #nano [Namafile]
```

Contoh:

```bash
[root@localhost sisjarlab] #nano pantun.txt
```

**B. Vi Editor**

Vi editor merupakan salah satu text editor yang awalnya dibuat untuk sistem operasi Unix. Nama Vi (dibaca "vee-ai") diambil dari singkatan *visual*. Vi editor sendiri merupakan text editor yang cepat dan powerful yang dikembangkan pertama kali oleh William (Bill) Joy.

1. Perintah dan Cara Kerja Vi Editor

Vi editor memiliki cara pengoperasian yang bersifat *screen-oriented* yang menggunakan terminal text editor. Pengoperasian Vi editor terbagi menjadi tiga mode, antara lain ialah Command Mode, Insert Mode, dan Command-Line Mode. Setiap melakukan perpindahan mode hanya dapat dilakukan pada Command Mode, sehingga tidak memungkinkan Insert Mode dapat berpindah menuju Command-Line Mode tanpa melalui Command Mode terlebih dahulu begitu pula dengan sebaliknya.

Berikut adalah penjelasan tiap mode:

**a. Command Mode**

Mode ini merupakan mode awal ketika Vi editor dijalankan. Fungsi yang dapat dilakukan pada mode ini antara lain, navigasi menggunakan cursor pada file yang ditulis, meng-edit baris dan kata, serta sebagai acuan perpindahan mode. Tidak seperti mode lainnya, perintah pada mode ini dapat dieksekusi tanpa perlu menekan enter. Untuk masuk ke dalam Vi editor dapat dilakukan dengan cara memasukkan command berikut pada terminal:

```bash
[root@localhost sisjarlab] #vi [Namafile]
```

Contoh:

```bash
[root@localhost sisjarlab] #vi lirik.txt
```

Setelah command di atas berhasil dieksekusi maka akan menampilkan file baru dengan nama file `lirik.txt` pada Vi editor, tampilan berikut merupakan tampilan pada command mode.

Perintah-perintah yang dapat dijalankan pada mode ini antara lain:

**Tabel 3.9.2.1 Perintah pada command mode**

| Kategori | Command | Description |
|---|---|---|
| Search | `n` | Ulangi pencarian sebelumnya pada cursor dan setelahnya. |
| Search | `N` | Ulangi pencarian sebelumnya pada cursor dan sebelumnya. |
| Delete | `dd` | Hapus semua teks pada baris cursor. |
| Delete | `ndd` | Hapus semua teks sejumlah n pada baris cursor. |
| Delete | `D` | Hapus semua teks setelah cursor. |
| Delete | `dw` | Hapus kata pada cursor berada. |
| Delete | `ndw` | Hapus kata sejumlah n pada cursor dan setelahnya. |
| Delete | `x` | Hapus karakter pada cursor. |
| Delete | `nx` | Hapus karakter sejumlah n pada cursor dan setelahnya. |
| Delete | `X` | Hapus karakter sebelum cursor. |
| Delete | `cw` | Hapus kata pada cursor sekaligus berpindah ke Insert Mode. |
| Replace (kemudian ketikkan) | `rn` | Menggantikan karakter pada cursor dengan n. |
| Replace (kemudian ketikkan) | `nr x` | Menggantikan karakter pada cursor dan setelahnya sejumlah n dengan karakter x. |
| Append (kemudian ketikkan) | `an` | Menambahkan n setelah cursor sekaligus berpindah ke Insert Mode. |
| Line | `o` | Menambahkan baris baru setelah baris cursor berada sekaligus berpindah ke Insert Mode. |
| Line | `O` | Menambahkan baris baru sebelum baris cursor berada sekaligus berpindah ke Insert Mode. |
| Undo/Repeat | `U` | Undo aktivitas pada baris cursor berada. |
| Undo/Repeat | `.` (tanda titik) | Lakukan perintah sebelumnya pada cursor. |
| Copy/Paste | `yy` | Salin baris pada baris dimana cursor berada. |
| Copy/Paste | `nyy` | Salin baris sejumlah n pada baris cursor berada dan setelahnya. |
| Copy/Paste | `p` | Menambahkan isi dari clipboard pada cursor berada dan setelahnya. |
| Cursor | Key panah kanan | Memindahkan cursor ke kanan. |
| Cursor | Key panah kiri | Memindahkan cursor ke kiri. |
| Cursor | Key panah atas | Memindahkan cursor ke atas. |
| Cursor | Key panah bawah | Memindahkan cursor ke bawah. |
| Cursor | `$` atau `[end]` | Memindahkan cursor ke akhir baris cursor berada. |
| Cursor | `w` | Memindahkan cursor ke kalimat setelah posisi cursor. |
| Cursor | `b` | Memindahkan cursor ke kalimat sebelum posisi cursor. |

Setiap penggunaan command di atas baik huruf kapital dan non kapital bersifat *case sensitive*.

**b. Insert Mode**

Insert Mode adalah mode yang memiliki fungsi untuk memasukkan karakter yang diketik ke dalam file yang telah dibuat sebelumnya. Perintah yang ada pada Command Mode dan Command-Line Mode tidak akan berfungsi.

Setelah berhasil membuat file dan masuk pada Command Mode, untuk berpindah mode menuju Insert Mode tekan huruf `i` pada keyboard, lalu tuliskan kata atau kalimat pada file tersebut.

Untuk keluar dari mode ini, gunakan key `[esc]`. Navigasi cursor pada Insert Mode menggunakan arrow key seperti pada Command Mode.

**c. Command Line Mode**

Mode ini memiliki cakupan fungsi yang lebih luas dalam memanipulasi atau menyunting file secara keseluruhan. Untuk masuk ke mode ini, masukkan karakter `:` atau `/` atau `?` lalu perintah yang akan digunakan. Untuk mengecek apakah sudah masuk ke dalam Command-Line Mode adalah dengan melihat bagian bawah pada Vi editor dimana cursor akan berpindah ke baris terbawah beserta karakter yang sudah diketikkan. Berbeda dengan Command Mode, mode ini akan mengeksekusi perintah setelah menekan enter. Mode ini tidak bisa mengeksekusi lebih dari satu baris perintah. Pada gambar di bawah, perintah yang dimasukkan merupakan perintah untuk menyimpan file dan keluar dari Vi editor.

Perintah-perintah yang dapat dijalankan pada mode ini antara lain:

**Tabel 3.9.2.2 Perintah pada command line mode**

| Command | Description |
|---|---|
| `:w` | Simpan perubahan file |
| `:w!` | Simpan perubahan file dan abaikan error yang muncul pada prosesnya |
| `:q` | Keluar dari Vi editor |
| `:q!` | Keluar dari Vi editor dan abaikan error yang muncul pada prosesnya |
| `:wq` | Simpan perubahan file kemudian keluar dari Vi editor |
| `/n` | Cari karakter atau kata n setelah cursor |
| `?n` | Cari karakter atau kata n sebelum cursor |
| `:s/n/m` | Cari karakter atau kata n setelah cursor, kemudian gantikan dengan m |

Ketika sudah berhasil menyimpan file, untuk menampilkan isi file yang sudah disimpan gunakan command:

```bash
[root@localhost sisjarlab]#cat [NamaFile]
```

Contoh:

```bash
[root@localhost sisjarlab]#cat lyrics.txt
```

Untuk menggabungkan beberapa file text editor menjadi satu file text editor, menggunakan command:

```bash
[root@localhost sisjarlab]#cat [namafile1.txt] [namafile2.txt] [namafile-n.txt] > [namafilebaru.txt]
```

Untuk mengetahui penjelasan lebih dari Vi editor dapat menggunakan command:

```bash
[root@localhost sisjarlab]#vimtutor
```

## IV. Lab Praktik

### 4.1 Instalasi Rocky Linux 8.6 Menggunakan VMWare

- 4.1.1 Buka VMWare Workstation Pro, lalu pilih *New Virtual Machine* dari menu File.
- 4.1.2 Pilih *Custom (Advanced)*, lalu klik Next.
- 4.1.3 Di bagian *Hardware Compatibility*, pilih *Workstation 16.x*, lalu klik Next.
- 4.1.4 Pilih "Installer disc image file (.iso)" dan klik Browse untuk mencari file installer (.iso) Rocky Linux di File Explorer. Setelah memilih file (.iso) Rocky Linux, klik Next.
- 4.1.5 Pada *Select a Guest Operating System*, pilih `Linux` untuk Guest operating system. Untuk Version, pilih `CentOS 7 64-bit`, lalu klik Next.
- 4.1.6 Di bagian *Virtual machine name*, masukkan nama Virtual machine yang diinginkan. Untuk praktikan, silahkan masukkan nama Virtual machine dengan format `Namapendek_NIM`. Pada *Location*, klik browse dan pilih folder untuk tempat instalasi Virtual machine. Kemudian, klik Next.
- 4.1.7 Pada *Processor Configuration*, pilih "1" untuk semua kolom. Setelah itu, klik Next.
- 4.1.8 Pada *Memory for the Virtual machine*, tentukan jumlah memori yang akan dialokasikan untuk Virtual machine. Selanjutnya, klik Next. Minimum Memory: 1GB dan Disarankan: 2GB atau 4GB untuk pengguna dengan laptop RAM 16GB.
- 4.1.9 Pada *Network Type*, pilih `Use network address translation (NAT)` supaya memungkinkan Virtual machine terhubung ke internet melalui PC/Laptop Anda. Kemudian, klik Next.
- 4.1.10 Pada *Select I/O Controller Types*, pilih `LSI Logic (Recommended)`. Kemudian, klik Next.
- 4.1.11 Pada *Select a disk Type*, pilih `SCSI (Recommended)`. Setelah itu, klik Next.
- 4.1.12 Pada *Select a disk*, pilih `Create a New Virtual disk`. Kemudian, klik Next.
- 4.1.13 Pada *Specify Disk Capacity*, masukkan kapasitas disk (dalam GB) yang akan dialokasikan untuk virtual machine. Disarankan menggunakan ruang sebesar yang direkomendasikan oleh VMWare, yaitu 20GB. Selanjutnya, pilih opsi "split virtual disk into multiple files", lalu klik Next.
- 4.1.14 Pada *Specify Disk File*, masukkan nama virtual machine disk (vmdk) sesuai dengan nama virtual machine. Kemudian, klik Next.
- 4.1.15 Pada *Ready to Create Virtual Machine* klik Finish.

### 4.2 Proses Instalasi Rocky Linux 8.6

- 4.2.1 Klik "Power on this virtual machine".
- 4.2.2 Klik "Install Rocky Linux 8" dan tekan enter.
- 4.2.3 Kemudian, tunggu sampai proses selesai.
- 4.2.4 Pada halaman *Welcome to Rocky Linux 8*, pilih bahasa "English" lalu klik Continue.
- 4.2.5 Pada *Localization*, pilih "Time & Date" dan pilih "Region: Asia, City: Jakarta" lalu klik Done.
- 4.2.6 Pada *System*, klik *Installation Destination* kemudian klik *Automatic* dan klik Done.
- 4.2.7 Selanjutnya, pilih *Network & Hostname* pada *System*.
- 4.2.8 Aktifkan jaringan Ethernet (`ens33`) untuk terhubung ke internet. Kemudian, ubah hostname menjadi `sisjarlab`. Setelah itu, klik Apply agar hostname dapat berubah dan tersimpan. Lalu, klik Done.
- 4.2.9 Selanjutnya, pilih *Root Password* pada *User Settings*. Lalu set Root Password lalu klik Done. Root password isikan dengan NIM masing-masing praktikan.
- 4.2.10 Selanjutnya, pilih *User Creation* pada *User Settings*. Lalu isikan Full name, Username, dan Password. Untuk Full name akan mengikuti Username dan isikan dengan `Namapendek_NIM`, untuk Password isikan dengan NIM masing-masing praktikan. Lalu klik Done.
- 4.2.11 Setelah melakukan semua konfigurasi, klik *Begin Installation* untuk memulai instalasi, lalu tunggu hingga selesai. Proses ini memakan waktu yang cukup lama, mohon untuk ditunggu saja hingga selesai.
- 4.2.12 Jika sudah klik *Reboot System*.
- 4.2.13 Lakukan Power On Virtual Machine.
- 4.2.14 Pada *Licensing*, klik *License Information*. Klik centang pada "I accept the license agreement", lalu klik Done.
- 4.2.15 Klik *Finish Configuration* pada pojok kanan bawah.
- 4.2.16 Kemudian akan muncul user yang sudah kita buat tadi.
- 4.2.17 Masukkan password yang sudah dibuat tadi. Kemudian klik Sign In.
- 4.2.18 Pada halaman *Welcome*, klik Next.
- 4.2.19 Pada halaman *Typing*, klik Next.
- 4.2.20 Pada halaman *Privacy*, aktifkan *Location Services*. Lalu klik Next.
- 4.2.21 Pada halaman *Online Account*, klik Skip.
- 4.2.22 Pada halaman *Ready to Go*, klik *Start Using Rocky Linux*.
- 4.2.23 Instalasi Rocky Linux dengan Desktop Environment GNOME selesai.

### 4.3 Text Editor

#### 4.3.1 Vi Editor

Nadya adalah seorang Mahasiswa Sistem Informasi yang tergabung dalam komunitas Cyan Music. Di sela-sela kesibukannya, ia terinspirasi untuk menulis sebuah lirik lagu yang berisi tentang curahan hatinya dalam menghadapi kedewasaan ini. Dengan menggunakan Vi Editor, Nadya menyimpan lirik tersebut dengan nama file `CHORUS.txt`.

```text
Persis setahun yang lalu
Ku dijauhkan dari yang tak ditakdirkan untukku
Yang kuingat saat itu
Yang kulakukan hanya menggerutu, Angkuh
Lebih percaya cara-caraku
Pilih ragukan rencana Sang Maha Penentu
```

Setelah selesai menulis lirik tersebut dan menyimpannya, Nadya teringat bahwa ia belum menulis intro dan versenya, maka dari itu Nadya membuat file baru dengan nama `VERSE.txt` kemudian menyimpannya.

```text
Untungnya bumi masih berputar
Untungnya ku tak pilih menyerah
Itu memang paling mudah
Untungnya kupilih yang lebih susah

Untungnya ku pakai akal sehat
Untungnya hidup terus berjalan
Untungnya ku bisa rasa
Hal-hal baik yang datangnya belakangan
Untungnya untungnya hidup harus tetap berjalan
```

Setelah selesai menulis lirik tersebut, Nadya menyatukan semua file menjadi file bernama `HIDUPTETAPHARUSBERJALAN.txt`.

## V. Daftar Pustaka

1. Laboratorium Sistem Operasi dan Jaringan Komputer. (2022). *Modul Praktikum Sistem Operasi 2022*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
2. Laboratorium Sistem Operasi dan Jaringan Komputer. (2023). *Modul Praktikum Sistem Operasi 2023*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.

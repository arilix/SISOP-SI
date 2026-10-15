# [M2] OS Process dan Linux Basic Administration

## I. Tujuan Praktikum

- I.1 Praktikan mampu memahami teori umum mengenai proses pada sistem operasi (OS Process).
- I.2 Praktikan mampu membuat repository baru dan melakukan pembaruan (update) repository melalui sistem operasi Rocky Linux 8.6.
- I.3 Praktikan mampu memahami dasar-dasar containerisasi menggunakan Docker pada sistem operasi Rocky Linux 8.6.
- I.4 Praktikan dapat menarik (pull) dan mengaplikasi image Docker.
- I.5 Praktikan mampu menjalankan perintah-perintah dasar pada Docker.
- I.6 Praktikan mampu memahami manajemen volume (volume management).
- I.7 Praktikan mampu menerapkan manajemen volume (volume management) menggunakan LVM (Logical Volume Management) melalui sistem operasi Rocky Linux 8.6.

## II. Alat dan Bahan

- II.1 Laptop
- II.2 ISO Rocky Linux 8.6
- II.3 VMWare Workstation 16.x
- II.4 Docker
- II.5 LVM

## III. Landasan Teori

### III.1 OS Process

#### III.1.1 Definisi

OS Process adalah sebuah program yang sedang dieksekusi. Proses adalah unit kerja terkecil yang secara individu mempunyai sumber daya dan dijadwalkan oleh sistem operasi. Sistem operasi berperan dalam mengelola semua proses yang berjalan dan mengalokasikan sumber daya yang diperlukan oleh proses tersebut. Dua atau lebih proses dapat berjalan secara bersamaan, dimana setiap proses mendapatkan bagian-bagian memori dan kendali sendiri-sendiri. Proses memiliki dua prinsip, yaitu *Independent* dan *One Program at any instant*. *Independent* berarti program-program tersebut tidak saling bergantung, sedangkan *One Program at any instant* berarti hanya satu proses yang dilayani oleh pemroses pada satu waktu.

Proses-proses yang dikelola oleh sistem operasi akan melalui serangkaian keadaan yang merupakan bagian dari aktivitasnya. Keadaan proses ini disebut sebagai status proses yaitu sebagai berikut.

| Status | Keterangan |
|---|---|
| New | Proses sedang dibuat. |
| Ready | Proses siap dieksekusi tetapi CPU belum tersedia karena sedang mengerjakan proses lain. |
| Waiting | Proses sedang menunggu suatu kejadian tertentu. Misalnya sedang menunggu operasi I/O selesai. |
| Running | Proses dieksekusi. Pada status ini, CPU sedang mengeksekusi instruksi-instruksi proses. |
| Terminated | Proses diakhiri. |

#### III.1.2 Konsep Pembuatan Proses

Adapun konsep pembuatan proses pada sistem operasi Linux adalah sebagai berikut.

a. Setiap proses diberi nomor khusus sebagai identifikasi yang disebut Process Identification atau PID berupa angka integer unik.
b. Jika proses selesai (terminated) maka semua sumber daya yang digunakan termasuk PID dibebaskan kembali.
c. Proses dibuat menggunakan system call `fork()` yang sering disebut forking process.
d. System call `fork()`, menyalin proses pemanggil sehingga terdapat dua proses yaitu PARENT (proses pemanggil) dan CHILD (proses hasil salinan).
e. Proses CHILD identik dengan proses PARENT-nya tetapi memiliki PID yang berbeda.
f. Setelah proses baru (CHILD) berhasil dibuat, eksekusi dilanjutkan secara normal di masing-masing proses pada baris setelah pemanggilan system call `fork()`.
g. Proses pemanggil (PARENT) dapat melakukan forking proses lebih dari satu kali sehingga memungkinkan terdapat banyak proses CHILD yang dieksekusi. Proses CHILD dapat melakukan forking process.

#### III.1.3 Process Management

Fungsi dari manajemen proses (process management) adalah untuk melihat, menjalankan, atau menghentikan proses-proses yang sedang berjalan ketika menjalankan sistem operasi. Berikut ini merupakan perintah-perintah umum yang digunakan ketika memanajemen proses.

**a. Command `ps`**

Process Status atau `ps` digunakan untuk menampilkan proses yang sedang aktif pada sistem. Command ini memiliki kekurangan yaitu tidak interaktif. Untuk mengeksekusi command `ps` dapat dilakukan pada terminal dengan cara sebagai berikut.

```bash
#ps
```

**b. Command `top`**

Command `top` digunakan untuk memanajemen proses Linux tanpa menggunakan GUI. Saat dieksekusi, maka akan menampilkan daftar semua proses yang sedang berjalan dan setiap detik akan diperbarui (default scanning yaitu 3 detik). Command ini lebih interaktif dibandingkan dengan command `ps`. Untuk mengeksekusi command `top` dapat dilakukan pada terminal dengan cara sebagai berikut.

```bash
#top
```

**c. Command `kill`**

Pada kasus tertentu, kita dapat menghentikan proses secara paksa. Misalnya ketika proses menggunakan sumber daya terlalu tinggi. Untuk mengeksekusi command `kill` dapat dilakukan pada terminal dengan cara sebagai berikut.

```bash
#kill [-signal] [PID]
```

Contoh:

```bash
#kill -9 6475
```

#### III.1.4 Network Configuration

Network Configuration diarahkan untuk melakukan konfigurasi interface yang terdapat didalam sistem operasi yang digunakan, khususnya untuk Administrator Server dengan menggunakan command line interface atau text user interface.

#### III.1.5 Ethernet Interface

Ethernet interface diidentifikasi oleh sistem menggunakan penamaan umum yaitu `ens33`. Ethernet interface ini dapat diubah sesuai dengan kebutuhan serta penggunaannya.

##### III.1.5.1 IP Addressing

a. **Network Manager Command Line Interface (NMCLI)**
   NMCLI adalah tool command line untuk mengontrol Network Manager. NMCLI dapat digunakan untuk menambahkan atau membuat IP address baru, memodifikasi IP address yang tersedia, dan menghapus IP address. Perubahan pada NMCLI bersifat sementara, sehingga pada saat sistem operasi melakukan restart, maka konfigurasi IP address akan kembali dalam keadaan seperti semula.

b. **Network Manager Text User Interface (NMTUI)**
   NMTUI adalah sebuah aplikasi TUI yang secara default ter-install pada Rocky Linux yang digunakan untuk melakukan modifikasi IP address pada Rocky Linux. Perubahan pada NMTUI bersifat permanen dan sangat disarankan untuk menggunakannya.

#### III.1.6 Repository Linux

##### III.1.6.1 Definisi

Repository Linux merupakan tempat penyimpanan dari sistem operasi Linux dan dapat digunakan sebagai tempat mengunduh (install) pembaruan dari sistem operasi. Repository Linux sendiri berisi paket-paket perangkat lunak yang disimpan di server dan dapat diakses melalui internet sehingga pengguna dapat meng-install dan memperbarui paket-paket tersebut pada sistem operasi Linux.

##### III.1.6.2 Jenis Repository

Repository paket di Linux dapat dikategorikan menjadi dua jenis utama, yaitu sebagai berikut.

**a. Official Repository**

Repository ini dikelola dan didistribusi oleh sistem operasi Linux. Contohnya seperti Ubuntu dan Debian. Ubuntu mengkategorikan repository resminya ke dalam empat komponen berikut.

- **Main**: Aplikasi yang didukung oleh Ubuntu dan dapat diunduh serta didistribusikan secara bebas.
- **Restricted**: Adanya kepemilikan perangkat lunak dan driver sehingga hanya pembuat aslinya yang dapat memperbaiki atau mengubahnya.
- **Universe**: Perangkat lunak dapat diakses oleh semua pengguna. Pemeliharaan dan pembaruan perangkat lunak dilakukan oleh komunitas, bukan pembuat resmi.
- **Multiverse**: Perangkat lunak memerlukan lisensi dan berbayar untuk digunakan dan didistribusikan.

**b. Third-Party Repositories**

Repository pihak ketiga adalah repository perangkat lunak yang dikelola secara independen dan tidak termasuk ke dalam official repository. Terdapat beberapa repository populer yang umumnya digunakan, yaitu sebagai berikut.

- **Ubuntu PPA (Personal Package Archive)**: Pengembang dapat menawarkan perangkat lunak versi terbaru secara langsung ke pengguna Ubuntu tanpa harus menunggu update dari official repository.
- **Arch User Repository (AUR)**: Komunitas yang dikelola repository untuk pengguna Arch Linux dengan menyediakan ribuan paket dan menawarkan akses perangkat lunak terbaru yang tidak tersedia dari official repository.
- **Debian's APT**: Sistem pengelolaan paket sudah sangat stabil dan teruji serta mampu menyediakan akses ke ribuan paket melalui repositori resmi Debian.
- **EPEL (Extra Packages for Enterprise Linux) Repository**: Repository yang menyediakan perangkat lunak berkualitas tinggi pada distribusi berbasis Red Hat, seperti CentOS, RHEL, dan Fedora. EPEL dapat membantu pengguna untuk menyediakan banyak pilihan perangkat lunak tanpa mengganggu stabilitas sistem.

##### III.1.6.3 Menambah EPEL Repository

Extra Packages for Enterprise Linux (EPEL) merupakan repository yang dibuat oleh Fedora Special Interest Group (SIGs) dan menyediakan perangkat lunak tambahan untuk RHEL (Red Hat Enterprise Linux) seperti CentOS. Repository ini digunakan untuk membuat paket Fedora berkualitas tinggi dan mampu digunakan di sistem RHEL dan CentOS. Command untuk menambahkan EPEL Repository adalah sebagai berikut.

```bash
#sudo dnf install epel-release
```

##### III.1.6.4 Memperbarui (update) EPEL Repository

Setelah menambah EPEL Repository, pengguna dapat melakukan pembaruan (update) paket dengan command sebagai berikut.

```bash
#sudo dnf update
```

#### III.1.7 Containerisasi

##### III.1.7.1 Container

Container adalah suatu unit atau wadah perangkat lunak dasar yang terdiri dari suatu kode dan dependensi sehingga aplikasi dapat berjalan dengan cepat dari satu lingkungan komputasi ke lingkungan lainnya, misalnya dari komputer atau server yang berbeda tanpa harus memerhatikan perbedaan sistem atau pengaturan.

Container merupakan teknologi virtualisasi yang bersifat lebih ringan dari Virtual Machine (VM). Container menggunakan Operation System (OS) yang sama dengan mesin host tempat container dijalankan sehingga lebih ringan dan cepat. Sedangkan Virtual Machine (VM) memiliki Operation System (OS) yang berjalan secara terpisah. Pada VM, OS utama (host) yang terdapat di komputer atau server dan Virtual Machine (VM) memuat OS tambahan yang terpisah secara keseluruhan.

Adapun kelebihan dan kekurangan dari container adalah sebagai berikut.

**a. Kelebihan container**

- Container dapat menjalankan aplikasi dan dependensinya tanpa harus menjalankan seluruh sistem operasi sehingga lebih ringan dan cepat dibandingkan Virtual Machine (VM).
- Bersifat portabilitas karena dapat dijalankan di berbagai lingkungan, seperti komputer lokal, server atau cloud tanpa perlu dimodifikasi.
- Bersifat skalabilitas karena mudah digandakan atau dipindahkan antar mesin untuk menjalankan permintaan beban kerja.
- Bersifat isolasi karena container berjalan secara terisolasi satu sama lain untuk menghindari konflik antar aplikasi.

**b. Kekurangan container**

- Container berjalan di tempat yang sama antara kernel OS dan host sehingga berisiko terhadap keamanan jika kernel host tidak aman.
- Container harus berjalan di kernel OS yang sama dengan host.
- Jika kernel host mengalami masalah, maka seluruh container yang berjalan berisiko terdampak.

##### III.1.7.2 Docker

Docker merupakan sebuah platform dan alat yang dapat mempermudah proses pembuatan, pengelolaan, dan menjalankan container. Pengembang dapat membungkus aplikasi ke dalam container yang bersifat ringan, cepat, dan mampu dijalankan di berbagai komputer dan server seperti Linux dan Windows.

Arsitektur Docker mengatur bagaimana cara kerja Docker yang di dalamnya memiliki beberapa komponen yang saling bekerja sama satu sama lain untuk menjalankan container.

a. **Docker Client**
   Client merupakan antarmuka (interface) yang digunakan oleh user untuk berinteraksi dengan Docker melalui command-line atau API.

b. **Docker Daemon**
   Daemon merupakan layanan yang berjalan di mesin host dan berfungsi untuk menjalankan perintah dari Docker Client. Docker Daemon berfungsi untuk membuat, mendistribusikan, dan menjalankan container dan images pada Docker.

c. **Docker Containers**
   Containers merupakan aplikasi yang berjalan di atas Docker dan dibuat oleh Docker Image dan dijalankan oleh Docker Daemon. Setiap perubahan yang terjadi di dalam container akan menambah lapisan (layer) baru dan aplikasi beserta dependensinya terisolasi.

d. **Docker Images**
   Images merupakan template yang bersifat read-only dan digunakan untuk membuat container. Image sendiri terdiri dari semua hal yang dibutuhkan untuk menjalankan aplikasi.

e. **Docker Registry**
   Registry merupakan tempat untuk menyimpan Docker Image, misalnya seperti Docker Hub yang bersifat publik dan pengembang dapat mengunduh (pull) serta mengunggah image. Docker Daemon akan memeriksa registry jika image yang diperlukan belum ada di sistem host.

##### III.1.7.3 Pull Image dan Membuat Container di Docker

**a. Pull Image**

Sebelum menjalankan container, Docker akan melakukan pengunduhan (pull) image ke lokal jika belum memiliki image melalui Docker Registry dengan command sebagai berikut.

```bash
#docker pull <nama_image>
```

Contoh:

```bash
#docker pull nginx
```

**b. Membuat container**

Apabila image sudah tersedia, Docker dapat membuat dan menjalankan container berdasarkan image tersebut. Container merupakan instance yang bersifat aktif dari image yang menjalankan aplikasi dengan command sebagai berikut.

```bash
#docker run <nama_image>
```

Contoh:

```bash
#docker run nginx
```

##### III.1.7.4 Perintah Dasar Docker

Terdapat beberapa perintah dasar (command) yang umumnya digunakan pada Docker, yaitu sebagai berikut.

a. Melihat daftar container yang sedang berjalan

```bash
#docker ps
```

b. Melihat semua container

```bash
#docker ps -a
```

c. Memulai container yang sudah ada

```bash
#docker start <nama_container>
```

d. Menghentikan container yang sedang berjalan

```bash
#docker stop <nama_container>
```

e. Menghapus container

```bash
#docker rm <nama_container>
```

f. Menghapus Docker image

```bash
#docker rmi <nama_image>
```

g. Menjalankan perintah di dalam container

```bash
#docker exec -it <nama_container> <command>
```

#### III.1.8 Volume Management

##### III.1.8.1 Definisi

Volume management merupakan suatu cara untuk mengelola dan mengatur pengalokasian penyimpanan, perluasan, hingga pemindahan ruang penyimpanan (storage) di dalam komputer. Tujuan dari volume management adalah memastikan data dapat diakses dengan mudah, meningkatkan efisiensi ruang penyimpanan, dan peningkatan kapasitas penyimpanan data.

##### III.1.8.2 Logical Volume Management (LVM)

Logical Volume Management (LVM) merupakan metode spesifik yang digunakan untuk menerapkan volume management di sistem operasi Linux. LVM memberikan kemudahan untuk mengelola dan memperbesar atau memperkecil ukuran partisi ruang penyimpanan (storage) di hard disk tanpa perlu memformat ulang atau menghentikan sistem.

Cara kerja Logical Volume Management (LVM) dalam mengatur dan mengelola penyimpanan di sistem operasi Linux adalah sebagai berikut.

a. **Physical Volume (PV)**
   Physical Volume (PV) merupakan disk fisik atau partisi disk yang sebenarnya. Misalnya seperti hard drive atau SSD yang tersedia di sistem.

b. **Volume Group (VG)**
   Beberapa physical volumes digabungkan menjadi satu dan disebut sebagai volume group. Volume Group (VG) direpresentasikan sebagai wadah yang menyatukan kapasitas dari beberapa physical volumes.

c. **Logical Volume (LV)**
   Volume group dapat dibuat menjadi beberapa logical volumes yang berperan sebagai partisi disk bersifat virtual sehingga dapat diatur ukurannya dan digunakan sebagai partisi biasa.

Sebagai contoh, jika memiliki tiga disk yang disebut sebagai physical volume yang memiliki kapasitas masing-masing 1 TB, kemudian digabungkan menjadi satu dan disebut sebagai volume group dengan total kapasitas 3 TB. Dari volume group tersebut dapat dibagi menjadi beberapa logical volumes, misalnya dibagi menjadi dua volume dengan masing-masing kapasitas 1,5 TB.

## IV. Lab Praktik

### IV.1 Test Koneksi Internet

**IV.1.1** Ketikan perintah `nmtui` lalu tekan Enter

```bash
[sisjarlabs@localhost ~]$ nmtui
```

**IV.1.2** Pilih opsi *Activate a connection*

**IV.1.3** Pastikan interface `ens33` sudah aktif

> *Untuk interface dari masing-masing virtual machine bisa saja berbeda.

**IV.1.4** Kembali ke menu utama, dan klik Ok

**IV.1.5** Ketikkan `ping 8.8.8.8` untuk mengecek koneksi

```bash
[sisjarlabs@localhost ~]$ ping 8.8.8.8
```

### IV.2 Instalasi Repository EPEL

**IV.2.1** Masuk ke mode root dan lakukan pengecekan apakah repository EPEL sudah ter-install pada VM atau belum ter-install

> *pada gambar dibawah repository EPEL belum ter-install

```bash
[root@localhost sisjarlab]# dnf repolist
```

**IV.2.2** Gunakan perintah berikut untuk memasang repository EPEL & update Rocky Linux.

```bash
[root@localhost sisjarlab]# dnf install epel-release -y
[root@localhost sisjarlab]# dnf update -y
```

> *tunggu hingga semua proses berhasil dilakukan.

**IV.2.3** Periksa kembali apakah repository EPEL sudah ter-install pada VM atau belum ter-install

```bash
[root@localhost sisjarlab]# dnf repolist
```

> *pada gambar dibawah repo EPEL sudah ter-install

### IV.3 Instalasi Docker

**IV.3.1** Tambahkan repo docker dengan command sebagai berikut.

```bash
[root@localhost sisjarlab]# sudo dnf config-manager --add-repo https://download.docker.com/linux/rhel/docker-ce.repo
```

**IV.3.2** Install Docker Engine, Containerd, dan Docker Compose

```bash
[root@localhost sisjarlab]# dnf -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin --allowerasing
```

Kemudian konfirmasi instalasi dengan command di atas tanpa `--allowerasing`

```bash
[root@localhost sisjarlab]# dnf -y install docker-ce docker-ce-cli containerd.io docker-compose-plugin
```

> *Command `allowerasing` digunakan untuk menghapus paket yang tidak bisa diinstal karena ada konflik dengan versi baru dari paket lain yang dibutuhkan

**IV.3.3** Nyalakan docker

```bash
[root@localhost sisjarlab]# systemctl start docker
```

**IV.3.4** Periksa status docker

```bash
[root@localhost sisjarlab]# systemctl status docker
```

> *Pastikan status docker pada kondisi active

**IV.3.5** Uji Coba Docker

Lakukan uji coba docker dengan perintah sebagai berikut.

```bash
[root@localhost sisjarlab]# docker run hello-world
```

### IV.4 Melakukan Pull Image NGINX di Docker

**IV.4.1** Pull Image NGINX

Setelah Docker ter-install, unduh image NGINX dengan mengetikkan perintah dan tunggu prosesnya sampai selesai.

```bash
[root@localhost sisjarlab]# docker pull nginx
```

**IV.4.2** Jalankan Container NGINX

Setelah berhasil mengunduh image NGINX, jalankan container dengan penamaan format `namapendek_nim` (Contoh: `evan_1202210206`)

```bash
[root@localhost sisjarlab]# docker run -d -p 8080:80 --name namapendek_nim nginx
```

**IV.4.3** Cek Container yang sedang berjalan

Setelah container berjalan, cek status container dengan perintah sebagai berikut.

```bash
[root@localhost sisjarlab]# docker ps
```

**IV.4.4** Akses Website yang Berjalan pada Container

Akses NGINX di browser menggunakan URL, buka firefox dan ketikkan `http://localhost:8080`

**IV.4.5** Stop dan Hapus Container

Untuk menghentikan container:

```bash
[root@localhost sisjarlab]# docker stop namapendek_nim
```

Setelah dihentikan, untuk menghapus container ketikan perintah:

```bash
[root@localhost sisjarlab]# docker rm namapendek_nim
```

Lalu cek kembali untuk container yang telah dibuat untuk membuktikan berhasil menghapus kontainer `namapendek_nim`, dengan ketikan perintah:

```bash
[root@localhost sisjarlab]# docker ps -a
```

**IV.4.6** Hapus Image NGINX

Setelah itu hapus image dengan perintah:

```bash
[root@localhost sisjarlab]# docker rmi nginx
```

### IV.5 Menambahkan Partisi

**IV.5.1** Tambahkan Partisi Penyimpanan VM

> *Pastikan untuk VM dalam keadaan mati...

Pada tampilan awal pilih masuk ke opsi *Edit virtual machine settings*.

Setelah itu masuk ke section *Hard Disk*, tekan *Expand...* dan isikan menjadi 25 (GB).

**IV.5.2** Cek penggunaan disk di Rocky Linux

Ketikkan command `df -h` untuk mengecek penggunaan disk di Rocky Linux

> *Pastikan masuk ke mode root untuk memudahkan pengerjaan

```bash
[root@localhost sisjarlab]# df -h
```

**IV.5.3** Menampilkan detail lengkap partisi yang terdeteksi sistem

Ketikkan command `fdisk -l`

```bash
[root@localhost sisjarlab]# fdisk -l
```

**IV.5.4** Modifikasi partisi disk pada Rocky Linux

Untuk melakukan modifikasi pada partisi di penyimpanan Rocky Linux ketikkan perintah berikut:

```bash
[root@localhost sisjarlab]# fdisk /dev/sda
```

**IV.5.5** Tambahkan partisi baru

Untuk menambahkan partisi baru ketikkan perintah berikut:

```bash
[root@localhost sisjarlab]# n
```

Lalu tambahkan partisi dengan tipe primary partition dengan menginputkan `p` dan untuk partisi number-nya default 3, setelah itu tekan Enter 2x

```text
Command (m for help) : n
Select (default p) : p
Partition number (3,4, default 3) : 3
```

**IV.5.6** Rubah Tipe Default dari Linux menjadi Linux LVM

Masukkan perintah `t` untuk masuk ke opsi tipe

```text
Command (m for help): t
```

Lalu untuk opsi partisi number masukkan 3

```text
Partition number (3,4, default 3) : 3
```

Dan untuk hex code masukkan `8e` untuk menjadi Linux LVM tipe partisinya

```text
Hex code (type L to list all codes) 8e
```

**IV.5.7** Simpan perubahan

Ketikkan perintah berikut untuk menyimpan

```text
Command (n for help) : w
```

**IV.5.8** Reboot VM

Lakukan reboot pada VM

**IV.5.9** Format partisi

Lakukan format partisi pada partisi yang sebelumnya sudah dibuat

> *Pastikan masuk ke mode root

```bash
[root@localhost sisjarlabs]# mkfs -t ext4 /dev/sda3
```

**IV.5.10** Cek partisi

Ketikkan perintah berikut untuk mengecek daftar disk dan partisi yang ada pada sistem.

```bash
[root@localhost sisjarlabs]# lsblk
```

> **LAKUKAN TAKE SNAPSHOT SEBAGAI BACKUP JIKA MENGALAMI KENDALA UNTUK MODUL SELANJUTNYA**

## V. Daftar Pustaka

1. Laboratorium Sistem Operasi dan Jaringan Komputer. (2015). *Modul Praktikum Sistem Operasi 2015*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
2. Laboratorium Sistem Operasi dan Jaringan Komputer. (2016). *Modul Praktikum Sistem Operasi 2016*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
3. Laboratorium Sistem Operasi dan Jaringan Komputer. (2019). *Modul Praktikum Sistem Operasi 2019*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
4. Laboratorium Sistem Operasi dan Jaringan Komputer. (2020). *Modul Praktikum Sistem Operasi 2020*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.

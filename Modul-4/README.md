# [M4] Web Server dan DNS Server

## 1. Tujuan Praktikum

- 1.1 Praktikan mampu memahami definisi dan cara kerja dari Web server, DNS server, dan DHCP server.
- 1.2 Praktikan mampu membuat Web server, DNS server, dan DHCP server local sederhana pada Virtual Machine Rocky Linux.
- 1.3 Praktikan mampu melakukan dan memahami konfigurasi sederhana mengenai Web server, DNS server, dan DHCP server pada Virtual Machine Rocky Linux.

## 2. Alat dan Bahan

- 2.1 Laptop
- 2.2 ISO Rocky Linux 8.6
- 2.3 VMWare Workstation 16.x

## 3. Landasan Teori

### 3.1 Web Server

#### 3.1.1 Definisi

Web server dapat mengacu pada dua hal, yaitu sebagai hardware ataupun software.

Yang pertama yaitu sebagai hardware. Pada sisi hardware, Web server adalah perangkat yang menyimpan software layanan Web dan juga file komponen-komponen sebuah Website, misal seperti file HTML, gambar, CSS, dan file JavaScript, yang tentunya server ini terhubung ke jaringan baik lokal maupun internet dan mendukung pertukaran data dengan perangkat lain yang terhubung ke layanan Web tersebut.

Jika dilihat dari sisi software, Web server adalah sebuah software yang menyediakan layanan Web kepada client yang melakukan request terhadap layanan tersebut, dan juga mengatur bagaimana sebuah Web user mengakses layanan tersebut, sesuai dengan protokol yang ada, misal HTTP ataupun HTTPS.

#### 3.1.2 Fungsi dan Cara Kerja Web Server

Fungsi utama dari Web Server yaitu menyimpan, memproses, dan memberikan halaman Web sesuai dengan permintaan dari Web user, atau client. Berikut merupakan cara kerja dari Web Server:

a. Pertama, user akan mengakses URL menggunakan Web browser. Ketika kita ingin mengakses sebuah Website biasanya kita membutuhkan Web browser, misal seperti Mozilla, Google Chrome, Internet Explorer dan lain sebagainya. Namun dalam kasus lain kita tidak memerlukan Web browser untuk mengirim HTTP Request. Misal kita ingin menguji layanan HTTP dari sebuah Web server, kita bisa menggunakan "Telnet" dan perintah `curl` pada OS Linux, menuju ke alamat Web server tersebut.
b. Selanjutnya, setelah user mengakses URL melalui Web browser, Web browser tersebut akan mengirimkan "HTTP Request" menuju Web server.
c. Kemudian Web server akan menerima request tersebut, dan menyiapkan file Website yang diminta lalu mengirimkan "HTTP Response" yang berisi file Website yang diperlukan oleh pengguna menuju ke Web browser.
d. Terakhir, Website bisa dilihat oleh user melalui Web browser. Perlu diketahui skema di atas baru berjalan apabila koneksi antara client menuju server dapat dipastikan terhubung dan juga settingan yang terdapat pada server tidak ada yang error. Untuk informasi error yang umumnya terjadi ketika mengakses sebuah Web server bisa dilihat di bawah ini:

**Table 3.1 Error Message**

| Jenis Error | Deskripsi |
|---|---|
| Error 403 (Server Forbidden) | Kita tidak diberi akses untuk melihat file (data dilindungi) pada laman situs, baik karena data disembunyikan atau dilindungi dengan kode pemrograman tertentu. Sehingga server akan menolak permintaan kita. |
| Error 404 (Server Not Found) | Beberapa hal yang menyebabkan terjadinya error ini: (a) data di database sebelumnya sudah ada, namun sudah dihapus atau dihilangkan dari database server; (b) terjadi gangguan akses Internet atau down; (c) jika akses Internet tetap gagal, maka kemungkinan halaman tersebut memang tidak ada; (d) terjadi kesalahan penulisan alamat URL. |
| Error 500 (Internal Server Error) | Kode error ini dapat diartikan sebagai adanya masalah atau kesalahan dalam server internal situs sehingga kita tidak bisa mengakses situs yang bersangkutan. |
| Error 502 (Bad Gateway) | Server bertindak sebagai gateway atau proxy dan menerima respon tidak valid dari server hulu. |
| Error 504 (Gateway Timeout) | Server bertindak sebagai gateway atau proxy dan tidak menerima respon yang tepat waktu dari server hulu. |
| Error 400 (Bad Request) | Error yang terjadi saat server tidak memahami permintaan dari pengunjung Website. Ketidakpahaman ini disebabkan karena permintaan tersebut tidak tepat atau mengalami corrupt di tengah proses pengiriman data. |
| Error 401 (Server Unauthorized) | Pesan kesalahan tersebut artinya user tidak memiliki otoritas atau izin untuk mengakses halaman Web tersebut. |

#### 3.1.3 Contoh Web Server

**a. NginX**

NginX adalah sebuah Web server kedua yang paling banyak digunakan saat ini, NginX atau bisa disebut Engine-X banyak digemari karena layanan server yang satu ini cukup stabil dan hemat resource. Hal tersebut menjadi alasan mengapa NginX menjadi Web server nomor dua yang paling banyak digunakan. Selain itu beberapa fitur NginX yang bisa lebih baik dalam menangani Website yang bertrafik tinggi menjadi nilai plus NginX.

**b. Apache Web Server**

Apache adalah layanan Web server yang paling populer. Berdasarkan survei W3Tech Top Ranks Web server di bulan Januari 2020, Apache adalah Web server yang paling banyak digunakan. Bahkan dari semua Web server yang ada, penggunaan Apache mencapai 41.5%. Hal tersebut dikarenakan software ini Open Source dan juga sangat fleksibel, Apache sendiri bisa digunakan untuk berbagai sistem operasi. Selain fleksibel, konfigurasi dan pengaturan Apache sangat mudah dan simple. Tidak ada pengaturan lebih lanjut untuk menggunakan Web server ini. Hal tersebut menjadi alasan banyak orang menggunakan Apache sebagai Web server.

**c. Litespeed Web Server**

Litespeed adalah sebuah Web server yang bisa dikatakan sebagai pusat kontrol Website yang memiliki performa terbaik. Hal tersebut terbukti dengan banyaknya penyedia Web hosting yang menggunakan Litespeed sebagai aplikasi Web server mereka. Litespeed memiliki banyak kelebihan diantaranya berupa kecepatan proses yang 50% lebih cepat dalam memproses PHP dan 6x lebih cepat dibandingkan Apache. Lalu kelebihan lain yang dimiliki oleh software ini adalah fitur anti DDOS yang sudah include, dan juga fitur fault recovery.

**d. Internet Information Server**

Internet Information Server adalah sebuah HTTP Web server yang digunakan dalam sistem operasi server Windows, mulai dari Windows NT 4.0 Server, Windows 2000 Server atau Windows Server 2003. Layanan ini merupakan layanan terintegrasi dalam Windows 2000 Server, Windows Server 2003 atau sebagai add-on dalam Windows NT 4.0. Layanan ini berfungsi sebagai pendukung protokol TCP/IP yang berjalan dalam lapisan aplikasi (application layer). IIS juga menjadi dasar dari platform Internet dan Intranet Microsoft, yang mencakup Microsoft Site Server, Microsoft Commercial Internet System dan produk-produk Microsoft BackOffice lainnya. Jadi Web server ini adalah Web server yang dibuat untuk sistem operasi Windows.

**e. Lighttpd**

Lighttpd (baca: lighty) adalah Web server open source terpopuler ketiga sejak dirilis ke publik pada tahun 2003. Seperti NginX yang "ringan", saat ini Lighttpd dipakai oleh 1% dari seluruh domain Web. Lisensi Lighttpd berada di bawah BSD dan bisa dijalankan di semua Operating System Unix dan Linux. Seperti NginX, Lighttpd juga adalah Web server "ringan" dan cepat yang sanggup melayani 10.000 klien secara simultan (concurrent connection). Faktor kurang besarnya komunitas dibandingkan NginX menjadi salah satu kekurangan Lighty dibandingkan NginX.

**f. Cherokee**

Cherokee dirilis pada tahun 2010 di bawah lisensi GNU General Public (GPL). Ini adalah Web server yang secara default sudah memiliki GUI (Graphical User Interface). Cherokee juga dapat dijalankan di Operating System Linux, Solaris bahkan Mac OS X dan Windows. Cherokee sudah mendukung teknologi populer di dunia Web server seperti FastCGI, SCGI, PHP, CGI, SSI, dan TLS/SSL. Fitur menarik yang melengkapinya adalah Virtual Host, Authentication, Load Balancing dan kompatibilitas dengan log Apache. Cherokee mendukung Zero Downtime saat Web server lain membutuhkan restart untuk perubahan konfigurasi. Satu lagi, ia mendukung keamanan saat mengunduh file (Secure Download) dengan men-generate URL sementara.

### 3.2 DNS Server

#### 3.2.1 Definisi Domain Name Server (DNS)

DNS (Domain Name System) adalah sistem yang bertanggung jawab untuk menerjemahkan nama domain yang mudah diingat menjadi alamat IP yang sesuai. Saat kita menjelajahi internet, kita sering menggunakan nama domain seperti www.google.com untuk mengakses situs web tertentu. Namun, komputer dan perangkat di dalam jaringan sebenarnya berkomunikasi melalui alamat IP (Internet Protocol), yang merupakan serangkaian angka yang sulit diingat oleh manusia. Inilah peran DNS: mengonversi nama domain yang kita masukkan ke dalam browser kita menjadi alamat IP yang dikenali oleh komputer atau server tempat situs web tersebut di-hosting. Dengan kata lain, DNS berfungsi sebagai buku telepon besar di internet yang memetakan nama domain ke alamat IP yang sesuai sehingga memungkinkan pengguna untuk mengakses situs web dengan mudah.

Selain itu, DNS juga memungkinkan kinerja internet yang efisien dengan menyimpan data penting tentang nama domain dalam bentuk rekaman DNS (DNS records) yang mencakup informasi seperti alamat IP, informasi server email, atau informasi lain yang diperlukan. Sistem ini terdiri dari beberapa komponen, termasuk server DNS yang tersebar di seluruh dunia dan melakukan tugas pemetaan nama domain ke alamat IP, serta resolver DNS yang ada di komputer atau perangkat kita yang bertanggung jawab untuk mengirim permintaan DNS ke server DNS untuk mendapatkan informasi yang diperlukan. DNS menjadi elemen kunci dalam infrastruktur internet yang memungkinkan pengguna untuk mengakses situs web dan layanan online dengan menggunakan nama domain yang mudah diingat, menjadikannya salah satu aspek fundamental dalam pengalaman menjelajah internet.

Contoh: Google.com memiliki alamat IP 172.217.0.142

#### 3.2.2 Fungsi Domain Name Server (DNS)

DNS memiliki beberapa fungsi diantaranya sebagai berikut:

a. Melakukan identifikasi alamat komputer di dalam suatu jaringan.
b. Sebagai penyedia alamat IP bagi tiap host.
c. Melakukan pendataan mail server.
d. Mentranskripsikan alamat domain.
e. Mempermudah user untuk tidak perlu mengingat alamat IP.

#### 3.2.3 Cara Kerja Domain Name Server (DNS)

a. Mencari alamat host pada file HOSTS, jika ada maka berikan alamatnya dan proses selesai.
b. Mencari pada data cache yang dibuat oleh resolver untuk menyimpan hasil permintaan sebelumnya, bila ada simpan dalam data cache, berikan hasilnya dan selesai.
c. Mencari pada alamat DNS server pertama yang telah ditentukan oleh pengguna. DNS server yang ditunjuk akan mencari nama domain pada cache-nya. Apabila tidak ketemu, pencarian dilakukan dengan melihat file database domain (zones) yang dimiliki oleh server. Apabila tetap tidak menemukan, maka server ini akan menghubungi DNS server lain yang sudah dikaitkan dengan server ini. Jika ditemukan simpan dalam cache dan berikan hasilnya.
d. Apabila pada DNS server pertama tidak ditemukan, pencarian dilanjutkan pada DNS server kedua dan seterusnya dengan proses yang sama seperti di atas.

#### 3.2.4 Struktur Domain Name Server (DNS)

Domain Name System (DNS) adalah bentuk database yang pengelolaannya secara lokal terhadap data yang akan diteruskan ke jaringan. Struktur DNS terbagi empat yaitu:

**a. Root-Level Domain**

Level paling atas atau tinggi pada struktur DNS dilambangkan dengan "." (titik).

**b. Top-Level Domain**

Domain ini adalah domain yang tingkatannya di bawah root, terletak pada label paling kanan. Contoh dari top-level domain adalah sebagai berikut:

- `.com`: organisasi komersial
- `.edu`: institusi pendidikan
- `.org`: organisasi non-profit
- `.net`: networks
- `.gov`: organisasi pemerintahan non-militer
- `.mil`: organisasi pemerintahan militer
- `.arpa`: Reverse DNS
- `.xx`: dua huruf untuk kode negara (id: Indonesia, my: Malaysia, dan lain-lain)

**c. Second-Level Domain**

Berisikan domain lain yang disebut subdomain. Contohnya `ac.id`, `co.id`, `gov.id`.

**d. Third-Level Domain**

- Third-level domain merupakan kata yang terletak sebelum second level domain. Third level domain biasa disebut juga dengan subdomain. Contohnya telkomuniversity.ac.id, mail.google.com, dan lain-lain.
- Hostname ini bisa menciptakan FQDN (Fully Qualified Domain Name) untuk setiap komputer. Bagian paling kiri dari bagian nama domain (biasanya) menyatakan nama host. Sisa dari nama domain menyatakan cara untuk membangun jalur logis untuk informasi yang dibutuhkan. Nama host adalah tujuan sebenarnya dari nama sistem yang dicari alamat IP-nya. Contoh: nama domain www.wikipedia.org memiliki nama host "www". Misal domain igracias.telkomuniversity.ac.id dimana igracias adalah hostname dan telkomuniversity.ac.id adalah domain name. Contoh FQDN:
  - Nama host: tune
  - Nama domain: telkomuniversity.ac.id
  - FQDN: tune.telkomuniversity.ac.id

#### 3.2.5 Elemen Dasar Domain Name Server (DNS)

**Table 3.2 Elemen Dasar Domain Name Server (DNS)**

| Elemen Dasar | Kegunaan / Definisi |
|---|---|
| NS (Name Server) | Digunakan untuk menyatukan "Authoritative Name server" yang mengelola domain. |
| (A) Address | Digunakan untuk memetakan suatu hostname ke suatu IP address. |
| PTR (Pointer) | Digunakan untuk meletakkan IP address ke hostname. |
| CNAME (Canonical Name) | Digunakan untuk menyatakan sebuah alias atau nickname dari suatu host. |
| MX (Mail Exchange) | Digunakan untuk mengarahkan email untuk suatu host atau domain ke host yang berfungsi sebagai mail server. |
| SOA (Start of Authority) | Perintah yang hanya digunakan oleh primary DNS. Perintah tersebut mendefinisikan awal dari suatu zone. |
| Nameserver | Nama domain dari sebuah Web server yang digunakan untuk mengarahkan domain ke server. |
| Serial_number | Nomor seri dari zone file. Biasanya menggunakan format yyyymmddxx (y: tahun, m: bulan, d: tanggal, x: kode serial). |
| Refresh_number | Mendefinisikan selang waktu yang diperlukan oleh secondary Name server untuk memeriksa perubahan zone file pada Primary Name server. |
| Retry_number | Mendeklarasikan berapa lama DNS menunggu pengulangan pengecekan terhadap DNS bila DNS tidak memberikan respon pada saat proses refresh. |
| Expire_number | Mendeklarasikan berapa lama zone file dipertahankan pada DNS apabila DNS tidak bisa, maka ia akan melakukan penghapusan. |
| Negative Cache TTL_number | Mendeklarasikan nilai default dari Time To Live (TTL) untuk semua resource pada zone file. |

## 4. Lab Praktik

> **BOLEH MENGGUNAKAN PUTTY ATAU TERMINAL PADA ROCKY LINUX**
>
> **JANGAN LUPA UNTUK MEMATIKAN FIREWALL PADA WINDOWS**

### 4.1 Instalasi Web Server dan DNS Server

#### 4.1.1 Instalasi Web Server (NginX)

1. Lakukan pengecekan apakah repository EPEL sudah terinstall pada VM atau belum terinstall:

> *pada gambar di modul, repo EPEL belum terinstall*

```bash
[root@sisjarlab sisjarlab]# yum repolist
```

2. Gunakan perintah berikut untuk memasang repository EPEL.

```bash
[root@sisjarlab sisjarlab]# dnf upgrade --refresh -y
[root@sisjarlab sisjarlab]# dnf install epel-release
```

> *tunggu hingga semua proses berhasil dilakukan*

3. Ubah hostname pada VM dengan perintah berikut:

```bash
[root@sisjarlab sisjarlab]# hostnamectl set-hostname rocky.sisjarlab.io
```

Keterangan: ganti semua kata "rocky" pada `rocky.sisjarlab.io` dengan **namapendek**. Contoh: `leon.sisjarlab.io`

4. Lakukan reboot dengan perintah berikut:

```bash
[root@sisjarlab sisjarlab]# reboot
```

5. Setelah reboot, gunakan perintah berikut untuk install Web server Nginx.

```bash
[root@rocky sisjarlab]# dnf install nginx
```

#### 4.1.2 Instalasi DNS Server (BIND)

1. Install BIND beserta tools-nya yang digunakan untuk DNS server dengan perintah berikut:

```bash
[root@rocky sisjarlab]# dnf install -y bind bind-utils
```

2. Lakukan **Take Snapshot** sebagai backup jika mengalami kendala di aktivitas selanjutnya.

### 4.2 Konfigurasi Web Server

> **HARAP DIPERHATIKAN**
>
> Ganti semua kata "rocky" pada `rocky.sisjarlab.io` dengan **namapendek** masing-masing. Contoh: `leon.sisjarlab.io`

Pada praktikum ini, akan dilakukan konfigurasi Web server dengan IP address static yaitu `10.10.80.1/25`. Adapun langkah-langkah konfigurasi Web server sebagai berikut:

1. Ubah *Network adapter 2* VM Rocky Linux menjadi **Host-only** atau **Custom: VMnet1 (Host-only)**.

2. Kemudian ubah IP address menjadi statik pada VM Rocky Linux menjadi `10.10.80.1/25` pada `ens37` dengan menggunakan perintah NMTUI:

```bash
[root@rocky sisjarlab]# nmtui
```

Isian pada NMTUI (Edit Connection untuk interface kedua):

```text
Profile name : ens37
Device       : ens37
IPv4 CONFIGURATION <Manual>
  Addresses   : 10.10.80.1/25
  Gateway     : 10.10.80.1
  DNS servers : 10.10.80.1
```

> Nama interface bisa berbeda pada setiap VM (misalnya `ens224`, bukan `ens37`). Cek dengan `nmcli device status`. Alternatif tanpa NMTUI ada di bagian [Solusi Error](#5-solusi-jika-mendapatkan-error).

3. Restart layanan network agar IP address berubah, dengan perintah berikut:

```bash
[root@rocky sisjarlab]# systemctl restart NetworkManager
```

4. Cek IP address apakah sudah berubah.

```bash
[root@rocky sisjarlab]# ifconfig
```

5. Jalankan Web Server dengan perintah berikut.

```bash
[root@rocky sisjarlab]# systemctl start nginx
[root@rocky sisjarlab]# systemctl enable nginx
```

Keterangan:

- Command `systemctl start nginx` digunakan untuk mengaktifkan service Nginx.
- Command `systemctl enable nginx` berfungsi agar service tersebut tetap berjalan walaupun adanya reboot atau biasa disebut sebagai daemon.

6. Cek Web Nginx dengan cara memasukkan IP address VM Rocky Linux pada Web Browser (Firefox).

7. Apabila belum berhasil mengakses Web Nginx di Web Browser, berhenti dan matikan service firewall dengan perintah di bawah ini, lalu cek lagi apakah sudah sesuai dengan poin nomor 6.

```bash
[root@rocky sisjarlab]# systemctl stop firewalld
[root@rocky sisjarlab]# systemctl disable firewalld
```

Keterangan:

- Command `systemctl stop firewalld` digunakan untuk menonaktifkan service firewalld.
- Command `systemctl disable firewalld` berfungsi pada saat dilakukan booting maka service firewall tersebut akan mati.

8. Buat direktori baru untuk Web server di `/usr/share/nginx` dengan nama `rocky.sisjarlab.io`

```bash
[root@rocky sisjarlab]# mkdir /usr/share/nginx/rocky.sisjarlab.io
```

9. Setelah itu buat file `index.html` pada direktori yang sebelumnya telah dibuat dengan cara seperti di bawah ini.

```bash
[root@rocky sisjarlab]# nano /usr/share/nginx/rocky.sisjarlab.io/index.html
```

Kemudian isi seperti di bawah ini dan simpan file tersebut.

**KETERANGAN: ganti `NAMA_NIM` dengan Nama Lengkap dan NIM. CONTOH: `ALFREDO LEON_1202210058`**

```html
<html>
<title> PRAKTIKUM SISTEM OPERASI 2024 </title>

Halo gusyy, akhirnya balik lagi nih di Praktikum SISOP MODUL 4
Udah lama banget nih ga ketemu sama asprak-asprak sisop yang baik hati
Oh iya coba deh kalian absen dulu, nama kamu siapa?
NAMA_NIM

</html>
```

10. Sebelum melakukan konfigurasi, backup file konfigurasi Nginx. Backup bertujuan agar saat konfigurasi gagal dapat dilakukan konfigurasi ulang tanpa remove/uninstall Nginx.

```bash
[root@rocky sisjarlab]# cp /etc/nginx/nginx.conf /etc/nginx/nginx.conf.backup
```

11. Buka file `nginx.conf` pada direktori `/etc/nginx/` untuk mengubah konfigurasi Nginx.

```bash
[root@rocky sisjarlab]# nano /etc/nginx/nginx.conf
```

12. Lakukan 3 tahapan berikut:

    1. Cari line yang bertuliskan `server_name  _;` kemudian ganti karakter `_` dengan hostname atau IP address static pada VM Rocky Linux. Sebagai contoh, VM Rocky Linux yang digunakan memiliki hostname `rocky.sisjarlab.io` dengan IP address `10.10.80.1`.
    2. Ganti lokasi Web server ke `/usr/share/nginx/rocky.sisjarlab.io/` yang sudah dibuat dengan cara ubah `root /usr/share/nginx/html;` menjadi `root /usr/share/nginx/rocky.sisjarlab.io;`
    3. Jika sudah selesai, simpan perubahan pada file.

Hasil akhir blok `server` pada `nginx.conf`:

```nginx
server {
    listen       80 default_server;
    listen       [::]:80 default_server;
    server_name  rocky.sisjarlab.io;
    root         /usr/share/nginx/rocky.sisjarlab.io;

    # Load configuration files for the default server block.
    include /etc/nginx/default.d/*.conf;

    location / {
    }
```

Keterangan:

- Berada pada line ke-41
- Gunakan shortcut dengan cara tekan `CTRL + Shift + -` (Minus) untuk mempermudah pencarian line.

13. Restart layanan Nginx dan pastikan status Nginx active atau running.

```bash
[root@rocky sisjarlab]# systemctl restart nginx
[root@rocky sisjarlab]# systemctl status nginx
```

14. Cek Web Browser Firefox, apakah Web Server sudah berubah.

> KETERANGAN: Disarankan untuk menghapus history, cache, dan cookies pada Web Browser terlebih dahulu.

### 4.3 Konfigurasi DNS Server

1. Sebelum konfigurasi, backup file konfigurasi BIND.

```bash
[root@rocky sisjarlab]# cp /etc/named.conf /etc/named.conf.backup
```

2. Buka file konfigurasi dasar BIND

```bash
[root@rocky sisjarlab]# nano /etc/named.conf
```

3. Ubah beberapa opsi berikut (pada blok `options`) sesuai dengan modul:

```text
options {
        listen-on port 53 { any; };
        listen-on-v6 port 53 { none; };
        directory       "/var/named";
        dump-file       "/var/named/data/cache_dump.db";
        statistics-file "/var/named/data/named_stats.txt";
        memstatistics-file "/var/named/data/named_mem_stats.txt";
        secroots-file   "/var/named/data/named.secroots";
        recursing-file  "/var/named/data/named.recursing";
        allow-query     { localhost; 10.10.80.0/25; };
```

> Perhatikan: pada `allow-query` yang ditulis adalah **alamat jaringan** `10.10.80.0/25`, bukan `10.10.80.1/25`. Lihat bagian [Solusi Error](#5-solusi-jika-mendapatkan-error) jika `named-checkconf` menolak konfigurasi.

4. Pada line paling akhir di konfigurasi, tambahkan line berikut.

```text
include "/etc/named/named.conf.local";
```

Posisi barisnya (di bagian paling bawah `named.conf`):

```text
include "/etc/named.rfc1912.zones";
include "/etc/named.root.key";
include "/etc/named/named.conf.local";
```

5. Buat file `named.conf.local` pada direktori `/etc/named` kemudian lakukan konfigurasi pada file `named.conf.local` seperti berikut:

```bash
[root@rocky sisjarlab]# touch /etc/named/named.conf.local
[root@rocky sisjarlab]# nano /etc/named/named.conf.local
```

```text
zone "rocky.sisjarlab.io" {
        type master;
        file "/etc/named/zones/db.rocky.sisjarlab.io";
};

zone "80.10.10.in-addr.arpa" {
        type master;
        file "/etc/named/zones/db.10.10.80";
};
```

6. Buat direktori `zones` pada direktori `/etc/named/` kemudian beri hak akses baca, tulis, dan eksekusi untuk user, sedangkan group dan other beri hak akses baca dan eksekusi.

```bash
[root@rocky sisjarlab]# mkdir /etc/named/zones
[root@rocky sisjarlab]# chmod 755 /etc/named/zones
```

7. Buat file untuk menyimpan konfigurasi *forward zone* pada direktori `/etc/named/zones/`.

```bash
[root@rocky sisjarlab]# touch /etc/named/zones/db.rocky.sisjarlab.io
```

8. Buka file yang telah dibuat pada langkah sebelumnya, kemudian lakukan konfigurasi pada file `db.rocky.sisjarlab.io` seperti di bawah ini.

```bash
[root@rocky sisjarlab]# nano /etc/named/zones/db.rocky.sisjarlab.io
```

```text
$TTL    604800
@       IN      SOA     ns1.rocky.sisjarlab.io.  root.rocky.sisjarlab.io. (
                  3     ; Serial
             604800     ; Refresh
              86400     ; Retry
            2419200     ; Expire
             604800   ) ; Negative Cache TTL

@       IN      NS      ns1.rocky.sisjarlab.io.
@       IN      A       10.10.80.1

ns1     IN      A       10.10.80.1
```

> **KETERANGAN: `ns1` (angka satu) BUKAN `nsl` (huruf L)**

9. Setelah itu, buat file untuk menyimpan konfigurasi *reverse zone* pada direktori `/etc/named/zones/`

```bash
[root@rocky sisjarlab]# touch /etc/named/zones/db.10.10.80
```

10. Buka file yang telah dibuat pada langkah sebelumnya, kemudian lakukan konfigurasi pada file `db.10.10.80` seperti di bawah ini.

```bash
[root@rocky sisjarlab]# nano /etc/named/zones/db.10.10.80
```

```text
$TTL    604800
@       IN      SOA     ns1.rocky.sisjarlab.io.  root.rocky.sisjarlab.io. (
                  3     ; Serial
             604800     ; Refresh
              86400     ; Retry
            2419200     ; Expire
             604800   ) ; Negative Cache TTL

@       IN      NS      ns1.rocky.sisjarlab.io.

1       IN      PTR     ns1.rocky.sisjarlab.io.
```

11. Jika sudah selesai menyimpan konfigurasi *forward* dan *reverse zone*, jalankan layanan DNS dengan perintah berikut.

```bash
[root@rocky sisjarlab]# systemctl start named
[root@rocky sisjarlab]# systemctl enable named
[root@rocky sisjarlab]# systemctl status named
```

Pastikan status `active (running)`. Pesan `network unreachable resolving '.'` pada log boleh diabaikan karena VM tidak terhubung ke root DNS server.

12. Untuk dapat menggunakan layanan DNS, tambahkan alamat DNS server pada file `/etc/resolv.conf`. Lalu tambahkan alamat nameserver yang baru di bawah line yang diawali dengan kata `search`.

```bash
[root@rocky sisjarlab]# nano /etc/resolv.conf
```

```text
# Generated by NetworkManager
search sisjarlab.io
nameserver 10.10.80.1
```

13. Selanjutnya coba apakah client berhasil mendapatkan layanan DNS dari server menggunakan perintah `nslookup`.

```bash
[root@rocky sisjarlab]# nslookup ns1.rocky.sisjarlab.io
[root@rocky sisjarlab]# nslookup 10.10.80.1
```

Hasil yang diharapkan:

```text
Server:         10.10.80.1
Address:        10.10.80.1#53

Name:   ns1.rocky.sisjarlab.io
Address: 10.10.80.1

1.80.10.10.in-addr.arpa name = ns1.rocky.sisjarlab.io.
```

14. Untuk menambahkan *record* baru seperti CNAME pada DNS cukup modifikasi file yang digunakan sebagai forward zone dan tambahkan *record* yang diinginkan.

```bash
[root@rocky sisjarlab]# nano /etc/named/zones/db.rocky.sisjarlab.io
```

Tambahkan di bawah record `ns1`:

```text
web     IN      CNAME   ns1
```

15. Kemudian reload BIND untuk menerapkan perubahan yang baru saja dilakukan dengan perintah berikut.

```bash
[root@rocky sisjarlab]# systemctl reload named
```

16. Ubah IP address network adapter VMnet1 pada main OS (Windows) seperti berikut ini:

| Pengaturan | Nilai |
|---|---|
| IP address | `10.10.80.2` |
| Subnet mask | `255.255.255.128` |
| Default gateway | `10.10.80.1` |
| Preferred DNS server | `10.10.80.1` |
| Alternate DNS server | (kosong) |

17. Buka command prompt pada main OS, lalu cek apakah DNS yang telah dibuat terdeteksi atau tidak dengan perintah berikut.

> *jika anda menggunakan LAN, maka IP yang didapat adalah IP network LAN itu sendiri, coba untuk menggunakan wifi atau tethering*

```text
C:\Users\...>nslookup
> ns1.rocky.sisjarlab.io
> rocky.sisjarlab.io
> 10.10.80.1
```

Hasil yang diharapkan: ketiganya dijawab oleh server `ns1.rocky.sisjarlab.io` (`10.10.80.1`) dengan alamat `10.10.80.1`.

> KETERANGAN: Ketik secara manual pada Command Prompt

18. Akses DNS server yang telah dikonfigurasi pada Web browser di main OS, misalnya `http://rocky.sisjarlab.io`. Halaman `index.html` yang dibuat sebelumnya akan tampil.

> KETERANGAN: Pastikan perangkat main OS tidak terhubung pada internet (*No Internet*) untuk melakukan cek DNS terdeteksi.

**LAKUKAN TAKE SNAPSHOT SEBAGAI BACKUP JIKA MENGALAMI KENDALA UNTUK MODUL SELANJUTNYA**

## 5. Solusi Jika Mendapatkan Error

Bagian ini tidak ada di modul asli. Isinya kumpulan error yang umum terjadi saat mengerjakan modul ini beserta solusinya.

### 5.1 `nmcli status` → `argument 'status' not understood`

Perintah `nmcli status` tidak ada. Gunakan:

```bash
nmcli device status
```

### 5.2 Interface `ens37` tidak ada

Nama interface ditentukan oleh VMware dan bisa berbeda (misalnya `ens160` dan `ens224`). Interface kedua (yang diset **Host-only/VMnet1**) adalah yang statusnya `disconnected`. Cek:

```bash
nmcli device status
ip a
```

Pakai nama interface yang muncul (misalnya `ens224`) sebagai pengganti `ens37`. Pastikan *Network Adapter 2* sudah ditambahkan dan VM sudah dinyalakan ulang setelahnya.

### 5.3 Mengatur IP statis tanpa NMTUI (nmcli)

Jika konfigurasi lewat NMTUI tidak muncul atau tidak tersimpan, gunakan `nmcli` (ganti `ens224` sesuai interface Anda):

```bash
nmcli connection add type ethernet ifname ens224 con-name server-lan
nmcli connection modify server-lan ipv4.method manual ipv4.addresses 10.10.80.1/25
nmcli connection modify server-lan ipv4.dns 10.10.80.1
nmcli connection modify server-lan ipv4.never-default yes connection.autoconnect yes
nmcli connection up server-lan
ip -4 addr show ens224
```

`ipv4.never-default yes` mencegah interface host-only ini mengambil alih rute internet VM. Hasil yang benar:

```text
inet 10.10.80.1/25 brd 10.10.80.127 scope global noprefixroute ens224
```

### 5.4 `ifconfig: command not found`

Pasang paket `net-tools`, atau pakai `ip`:

```bash
dnf install net-tools -y
ip -4 addr show
```

### 5.5 Isi `index.html` malah tampil di terminal / file tidak terisi

Kalau `nano` tertutup lalu isi HTML diketik langsung di prompt (`root@rocky:~# <!DOCTYPE html>...`), isinya **tidak** tersimpan ke file. Buat file dengan salah satu cara berikut:

```bash
nano /usr/share/nginx/rocky.sisjarlab.io/index.html
```

atau langsung dari terminal:

```bash
cat > /usr/share/nginx/rocky.sisjarlab.io/index.html <<'EOF'
<html>
<title> PRAKTIKUM SISTEM OPERASI 2024 </title>
Isi halaman Anda, NAMA_NIM
</html>
EOF
```

Cek isinya: `cat /usr/share/nginx/rocky.sisjarlab.io/index.html`

### 5.6 Nginx gagal start / halaman tidak berubah

Selalu uji sintaks sebelum restart:

```bash
nginx -t
systemctl restart nginx
systemctl status nginx
curl http://10.10.80.1
```

- Jika `nginx -t` error, periksa tanda `;` di akhir tiap baris `server_name` dan `root`.
- Jika konfigurasi sudah benar tapi browser masih menampilkan halaman lama, hapus cache/cookies browser atau tes dengan `curl`.
- Jika terjadi `403 Forbidden` pada direktori kustom, cek izin direktori (`ls -ld /usr/share/nginx/rocky.sisjarlab.io`) dan konteks SELinux: `restorecon -Rv /usr/share/nginx/rocky.sisjarlab.io`.
- Jika konfigurasi rusak, kembalikan backup: `cp /etc/nginx/nginx.conf.backup /etc/nginx/nginx.conf`.
- Jika tidak bisa diakses dari browser/Windows, pastikan firewall VM mati (`systemctl stop firewalld`) dan firewall Windows juga dimatikan.

### 5.7 `named-checkconf`: `address/prefix length mismatch` dan `named` gagal start

Contoh error:

```text
/etc/named.conf:19: '10.10.80.1/25': address/prefix length mismatch '25'
Job for named.service failed because the control process exited with error code.
```

Penyebab: pada `allow-query` ditulis `10.10.80.1/25` (alamat host), padahal dengan prefix `/25` BIND mengharuskan **alamat jaringan** `10.10.80.0/25`. Perbaikan:

```bash
nano /etc/named.conf
```

```text
allow-query     { localhost; 10.10.80.0/25; };
```

Lalu periksa dan jalankan:

```bash
named-checkconf
named-checkzone rocky.sisjarlab.io /etc/named/zones/db.rocky.sisjarlab.io
named-checkzone 80.10.10.in-addr.arpa /etc/named/zones/db.10.10.80
systemctl enable --now named
systemctl status named
```

`named-checkconf` tanpa keluaran berarti konfigurasi benar. Jika `named` masih gagal, lihat penyebab detailnya:

```bash
journalctl -u named -n 30 --no-pager
```

Penyebab umum lainnya: titik koma `;` kurang, kurung `{ }` tidak berpasangan, nama file zone tidak sama dengan yang ditulis di `named.conf.local`, atau lupa titik di akhir nama domain pada file zone (misal `ns1.rocky.sisjarlab.io.`).

### 5.7b Query ditolak (`REFUSED`) karena `allow-query`

Jika `nslookup` dari Windows/klien lain menghasilkan `REFUSED` atau `query refused`, padahal `named` sudah `active (running)`, berarti alamat klien tidak termasuk di daftar `allow-query` (misalnya IP klien di luar `10.10.80.0/25`). Agar query dari mana pun diizinkan, ubah `allow-query` menjadi `any`:

```bash
nano /etc/named.conf
```

```text
allow-query     { any; };
```

Lalu periksa dan muat ulang:

```bash
named-checkconf
systemctl restart named
```

Pastikan firewall juga mengizinkan DNS:

```bash
firewall-cmd --permanent --add-service=dns
firewall-cmd --reload
```

> `any` mengizinkan semua alamat untuk melakukan query, jadi gunakan hanya di lingkungan praktikum/host-only. Untuk lingkungan nyata, batasi dengan `{ localhost; 10.10.80.0/25; };`.

### 5.8 Log `named`: `network unreachable resolving './NS/IN'`

Ini normal untuk jaringan host-only tanpa internet (BIND mencoba menghubungi root server). Selama status `active (running)` dan `nslookup` ke server lokal berhasil, abaikan.

### 5.9 `nslookup` gagal atau jawabannya salah

- Uji langsung ke server lokal agar tidak bergantung pada resolver sistem:

```bash
nslookup rocky.sisjarlab.io 127.0.0.1
nslookup 10.10.80.1 127.0.0.1
```

- `NXDOMAIN` / `can't find`: periksa nama domain pada `named.conf.local` dan nama file zone harus sama persis dengan yang ada di `/etc/named/zones/`.
- Setiap mengubah file zone (misalnya menambah CNAME), **naikkan nomor Serial** di bagian SOA (misal `3` menjadi `4`), lalu `named-checkzone ...` dan `systemctl reload named`. Tanpa menaikkan serial, perubahan sering tidak terbaca.
- Record CNAME dengan nama relatif (`web IN CNAME ns1`) otomatis menjadi `ns1.rocky.sisjarlab.io.`. Jika menulis nama lengkap, wajib diakhiri titik.
- Perbedaan `ns1` (angka satu) dengan `nsl` (huruf L) sering menjadi penyebab.

### 5.10 `/etc/resolv.conf` kembali seperti semula

File itu dibuat otomatis oleh NetworkManager, jadi perubahan manual bisa tertimpa. Set lewat NetworkManager agar permanen:

```bash
nmcli connection modify server-lan ipv4.dns 10.10.80.1 ipv4.dns-search sisjarlab.io
nmcli connection up server-lan
cat /etc/resolv.conf
```

Jika ada beberapa `nameserver`, yang pertama di daftar yang dipakai dulu. Gunakan `nslookup <nama> 10.10.80.1` untuk memastikan server lokal yang dipakai.

### 5.11 Windows tidak bisa mengakses domain

1. Pastikan IP adapter **VMware Network Adapter VMnet1** `10.10.80.2/255.255.255.128` dan DNS `10.10.80.1`.
2. `ping 10.10.80.1` harus berhasil (matikan firewall Windows jika gagal).
3. Uji DNS langsung ke server: `nslookup rocky.sisjarlab.io 10.10.80.1`
4. Bersihkan cache DNS Windows: `ipconfig /flushdns`
5. Jika `nslookup` berhasil tetapi browser tidak, pastikan alamat diketik `http://rocky.sisjarlab.io` (bukan `https`), nonaktifkan *Secure DNS* / DNS over HTTPS di browser, dan matikan sementara koneksi internet/Wi-Fi lain (sesuai catatan modul) agar Windows tidak memakai DNS lain.
6. Default gateway `10.10.80.1` pada adapter VMnet1 boleh dikosongkan jika Windows kehilangan internet, karena adapter host-only hanya menghubungkan Windows dengan VM pada subnet yang sama.

## 6. Daftar Pustaka

1. Laboratorium Sistem Operasi dan Jaringan Komputer. (2015). *Modul Praktikum Sistem Operasi 2015*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
2. Laboratorium Sistem Operasi dan Jaringan Komputer. (2016). *Modul Praktikum Sistem Operasi 2016*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
3. Laboratorium Sistem Operasi dan Jaringan Komputer. (2019). *Modul Praktikum Sistem Operasi 2019*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
4. Laboratorium Sistem Operasi dan Jaringan Komputer. (2020). *Modul Praktikum Sistem Operasi 2020*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.

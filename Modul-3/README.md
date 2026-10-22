# [M3] Remote Access dan Bash Scripting

## I. Tujuan Praktikum

- 1.1 Praktikan mampu memahami dan menguasai mengenai konsep serta perintah dasar BASH Scripting.
- 1.2 Praktikan mampu mengaplikasikan contoh penggunaan BASH Scripting dalam Operating System Rocky Linux 8.6.
- 1.3 Praktikan mampu memahami dan menguasai konsep SSH serta mengaplikasikannya pada Operating System Rocky Linux 8.6.

## II. Alat dan Bahan

- 2.1 PC/Laptop
- 2.2 ISO Rocky Linux 8.6
- 2.3 VMWare Workstation 16.x
- 2.4 PuTTY 0.77

## III. Landasan Teori

### 3.1 Remote Access

#### 3.1.1 Definisi

Remote access adalah kemampuan komputer untuk mengendalikan host atau client dengan memanfaatkan port, dimana administrator dapat mengontrol komputer client, berinteraksi dengan user, backup data, atau aktivitas lainnya. Untuk melakukan aktivitas tersebut komputer administrator tidak perlu terkoneksi secara fisik untuk mengendalikan komputer host atau client. Artinya dengan remote access kita bisa mengontrol dari jarak jauh.

#### 3.1.2 Remote Access Control

**a. Telnet**

Telnet (Telecommunication Network Protocol) merupakan sebuah protocol yang digunakan untuk menghubungkan suatu sistem dengan sistem lainnya secara remote dengan menggunakan koneksi virtual terminal melalui jaringan. Telnet terdiri dari client dan server. Adapun beberapa kelebihan dan kekurangan dari Telnet diantaranya:

- Kelebihan Telnet
  1. Mudah dalam akses komputer dari jarak yang jauh, sehingga seolah-olah penggunanya mengeksekusi perintah command line pada komputer tersebut.
  2. Hemat dari segi penggunaan bandwidth karena hanya mengirimkan data berupa teks.
  3. Ukuran kecil dan ringan. Telnet memiliki ukuran protokol yang relatif kecil, sehingga tidak membebani resource komputer atau jaringan yang digunakan.

- Kekurangan Telnet
  1. Telnet menggunakan New Technology LAN Manager sebagai sistem otentikasi, tetapi New Technology LAN Manager pada Telnet tidak dilengkapi dengan enkripsi, sehingga data login yang dikirimkan dalam bentuk teks biasa mudah disadap.
  2. Tidak menjamin integritas data karena data dikirim tanpa perlindungan, integritas data yang ditransmisikan tidak terjamin, sehingga rentan terhadap manipulasi atau perubahan oleh pihak tidak berwenang.
  3. Rentan terhadap pencurian password dikarenakan tanpa enkripsi, informasi kredensial (username dan password) yang dikirim melalui Telnet dapat dicuri oleh "sniffers" (perangkat lunak atau alat yang menyadap lalu lintas data), meningkatkan risiko akses tidak sah.

**b. Secure Shell**

SSH (Secure Shell) merupakan protocol jaringan yang memungkinkan pertukaran data antara dua komputer secara aman. Berbeda dengan Telnet yang menggunakan plain text, SSH melakukan enkripsi data selama proses komunikasi sehingga menutup celah bagi penyusup (intruder) untuk mendapatkan password yang tidak terenkripsi.

- Fungsi SSH
  1. Login ke shell pada remote host (menggantikan Telnet dan rlogin).
  2. Mengeksekusi satu perintah pada remote host (menggantikan RSH).
  3. Menyalin file dari local server ke remote host.

- Kelebihan SSH
  1. Data yang dipertukarkan ketika melakukan remote akan terenkripsi.
  2. Memiliki kode khusus untuk mengidentifikasi client.

- Kekurangan SSH
  1. Rentan terhadap serangan Man-in-the-Middle Attack.
  2. Ketergantungan pada koneksi internet.

**c. Remote Login**

Remote Login (rlogin) adalah salah satu layanan internet yang memungkinkan seorang pengguna internet untuk mengakses (login) ke sebuah remote host dalam lingkungan jaringan internet. Dengan memanfaatkan remote login, user dapat mengoperasikan sebuah host dari jarak jauh tanpa harus secara fisik berhadapan dengan host. User juga dapat melakukan pemeliharaan/maintenance, menjalankan sebuah program, atau bahkan melakukan instalasi program baru di remote host.

- Kelebihan rlogin:
  1. Protocol yang lebih dulu hadir daripada protocol lain.
  2. Memiliki akses remote ke Server Jaringan.

- Kekurangan rlogin:
  1. Tingkat keamanan yang lebih rendah dari protocol lain.
  2. Tidak ramah pengguna.

**d. PuTTY**

PuTTY merupakan aplikasi open source yang mendukung banyak protocol jaringan seperti SSH, Telnet, SCP, rlogin, serial port, dan raw socket connection. Protocol ini dapat digunakan untuk menjalankan remote session pada sebuah komputer melalui sebuah jaringan baik LAN maupun internet.

Keterangan Gambar 3.1.2.1 (PuTTY Interface):

1. Nama Host atau IP Address tujuan
2. Port Address tujuan
3. Tipe koneksi
4. Sesi yang tersimpan
5. Daftar sesi
6. Jenis penutupan jendela kerja

### 3.2 Bash Script

#### 3.2.1 Definisi

BASH (Bourne Again Shell) adalah shell Unix dan bahasa perintah yang ditulis oleh Brian Fox untuk Proyek GNU sebagai pengganti perangkat lunak gratis untuk shell Bourne, pertama kali dirilis pada tahun 1989 ini telah digunakan secara luas sebagai shell login default untuk sebagian besar distribusi Linux dan MacOS Apple (OS X). BASH juga dapat membaca dan menjalankan perintah dari file, yang disebut skrip shell. BASH membutuhkan user untuk memasukkan sebuah command yang dapat menghasilkan suatu action.

#### 3.2.2 Perintah Dasar

**a. Cat**

Menampilkan isi file tanpa harus masuk ke dalam suatu editor.

Contoh:

```bash
[sisjar@sisjarlab ~]$ cat data.sh
```

Melihat isi file teks dari "data.sh"

**b. Chmod**

Mengganti permission dari suatu file.

Contoh:

```bash
[sisjar@sisjarlab ~]$ chmod +x dasisop.sh
```

Merubah hak akses file "dasisop.sh" agar dapat dieksekusi

**c. Redirection**

Mengirim output ke suatu file atau menerima input dari suatu file menggunakan operator `<`.

Contoh:

```bash
[sisjar@sisjarlab ~]$ cat < semesterlima.txt
```

Menggunakan isi file "semesterlima.txt" sebagai input oleh perintah cat

**d. Grep**

Mencari suatu baris string tertentu dan berguna untuk mempercepat pencarian.

Contoh:

```bash
[sisjar@sisjarlab ~]$ grep sisjar /etc/passwd
```

Mencari user "sisjar" pada "/etc/passwd"

**e. Pipe**

Membuat output suatu perintah menjadi input perintah lain dengan menggunakan operator `|`.

Contoh:

```bash
[sisjar@sisjarlab ~]$ cat data.sh | grep echo
```

Menampilkan isi "data.sh" kemudian mencari baris string yang mengandung kata echo

**f. Sed (Stream Editor)**

Utilitas dari Unix yang mem-parsing dan mengubah teks menggunakan bahasa pemrograman yang sederhana dan ringkas.

Contoh:

```bash
[sisjar@sisjarlab ~]$ sed 's/teks_lama/teks_baru/flag' namafile
```

Penjelasan:

1. `s` adalah perintah untuk mengganti (substitusi)
2. `s` bisa ditambahkan dengan angka
3. Flag yang umum digunakan adalah:
   - `/g` untuk menggantikan seluruh kata yang ditemukan
   - `/p` untuk mencetak baris yang telah dimodifikasi, hasilnya akan mengalami duplikasi
   - `/n` diisi oleh angka (`/1`, `/2`, `/3`, `/..`) dan penggantian kata dikhususkan untuk baris tertentu

**g. Man**

Menampilkan penjelasan mengenai perintah yang digunakan.

Contoh:

```bash
[sisjar@sisjarlab ~]$ man ls
```

Menjelaskan apa saja fungsi yang dapat dilakukan oleh perintah ls

**h. Wc**

Menghitung jumlah baris, kata atau karakter dari file yang diberikan fungsi oleh perintah wc.

- `-c`, `--bytes` untuk menghitung jumlah byte
- `-m`, `--chars` untuk menghitung jumlah karakter
- `-l`, `--lines` untuk menghitung jumlah baris
- `-L`, `--max-line-length` untuk menghitung baris paling panjang
- `-w`, `--words` untuk menghitung jumlah kata

Contoh:

```bash
[sisjar@sisjarlab ~]$ wc -w data.txt
```

**i. Date**

Menampilkan tanggal dan jam saat ini, pada date terdapat beberapa jenis output yang berbeda, dengan menggunakan perintah tambahan disamping date. Perintah tambahan tersebut menggunakan tanda `+%` kemudian diikuti oleh karakter khusus. (Gunakan perintah `man date` untuk mengetahui jenis output lainnya).

Contoh:

```bash
[sisjar@sisjarlab ~]$ date +%a
```

Menampilkan hari apa sekarang

#### 3.2.3 Mode

**a. Mode Non-Interaktif**

Pada mode ini, user dapat menuliskan beberapa perintah dalam sebuah file script untuk dieksekusi oleh BASH. BASH tipe ini dapat diaktifkan dengan hanya menjalankan nama file yang berisikan script tersebut. Berikut adalah contoh dari penggunaan mode non-interaktif, yaitu dengan cara membuat dan menjalankan satu BASH script sederhana.

```bash
#!/bin/bash
echo "Hello World!"
echo "Anda sedang berada di direktori $pwd"
```

Kemudian simpan file dan ubah hak akses file tersebut agar dapat dieksekusi

```bash
[sisjar@sisjarlab ~]$ chmod +x Where.sh
```

Jalankan shell script

```bash
[sisjar@sisjarlab ~]$ ./Where.sh
```

Maka hasil yang akan keluar adalah:

```text
Hello World!
Anda sedang berada di direktori /home/sisjar
```

**b. Mode Interaktif**

Mode ini dijalankan oleh BASH shell dengan menunggu perintah dari user. Kemudian memeriksa shell yang sedang aktif dan seketika setelah user menekan tombol Enter, perintah tersebut dikerjakan oleh BASH. Setelah selesai, BASH siap menerima perintah dari user lagi. Pada mode ini, BASH akan meminta user untuk menginputkan suatu kata atau jawaban yang akan disimpan oleh sistem yang mana nantinya akan ditampilkan.

Mode ini membutuhkan respons user untuk mengolah script dan menampilkan hasilnya. Mode ini dapat dikenali dengan melihat kata `read` pada script yang nantinya dapat dipanggil sebagai variable. Contoh dari penggunaan mode ini adalah, pertama-tama buatlah sebuah file BASH dengan nama "Hai.sh", kemudian ketikkan script berikut:

```bash
#!/bin/bash
echo -e "Hi, What is your name? : \c"
read name
echo "Hi, $name"
```

Kemudian simpan file dan ubah hak akses file tersebut agar dapat dieksekusi

```bash
[sisjar@sisjarlab ~]$ chmod +x Hai.sh
```

Maka hasil yang akan keluar adalah:

```text
Hi, What is your name? : Cynthia
Hi, Cynthia
```

#### 3.2.4 Penggunaan Variable

Secara sederhana variable adalah pengenal (identifier) berupa satuan dasar untuk menyimpan nilai yang sewaktu-waktu dapat berubah baik oleh eksekusi program (Runtime Program) ataupun proses lain yang dilakukan sistem operasi. BASH Scripting memiliki 3 jenis variabel, berikut merupakan jenis-jenis variable:

**a. Environment Variable**

Environment Variable adalah variable yang khusus digunakan oleh shell atau sistem Linux untuk proses kerja sistem, seperti variable `HOME`, `HOSTNAME`, `USER`, `SHELL`, dan masih banyak lagi. Untuk melihat seluruh nama variable environment yang terdapat pada BASH Scripting gunakan perintah `env`.

**b. Positional Parameter**

Positional Parameter adalah variable yang digunakan oleh shell untuk menampung argument yang akan diberikan kepada shell berupa argument saat sebuah file dijalankan.

**Tabel 3.2.4 Variable pada BASH Scripting**

| Deskripsi | Operator | Keterangan |
|---|---|---|
| Equal | `-e` | Sama dengan (=) |
| Not Equal | `-ne` | Tidak sama dengan (!=) |
| Less than | `-lt` | Lebih kecil dari (<) |
| Less or Equal | `-le` | Lebih kecil atau sama dengan (<=) |
| Greater than | `-gt` | Lebih besar dari (>) |
| Greater or Equal | `-ge` | Lebih besar atau sama dengan (>=) |

**c. User Defined Variable**

User Defined Variable adalah variable yang didefinisikan sendiri oleh programmer sesuai dengan kebutuhan, ada beberapa hal yang harus diperhatikan dalam mendefinisikan variable:

- Dimulai dengan huruf atau underscore
- Hindari penggunaan karakter tertentu seperti `*`, `#`, `$` dan lainnya.
- BASH bersifat case sensitive, dalam kata lain dapat membedakan huruf besar dan kecil.

#### 3.2.5 Penggunaan Parameter

Parameter dalam shell digunakan untuk menampung nilai yang diberikan terhadap shell dalam sebuah variabel khusus. Dalam shell parameter terdapat maksimal 9 buah. Lambang dari penggunaan parameter adalah tanda `$`.

#### 3.2.6 Simple I/O (Input/Output)

Dalam konteks BASH, input mengacu pada data atau informasi yang diterima atau dibaca oleh suatu program, sedangkan output mengacu pada informasi atau data yang dihasilkan atau ditulis oleh suatu program.

Contohnya ialah statement `echo` yang menampilkan teks atau informasi ke layar, atau operasi redirect ke file. Selain `echo`, BASH menyediakan perintah built-in `printf` untuk mengalihkan output ke output standard, baik ke layar ataupun ke file dengan format tertentu, mirip dengan statement `printf` milik bahasa C atau perl. BASH I/O mencakup area operasi input dan output yang luas. Terdapat beberapa saluran standar yang biasanya digunakan untuk mengelola input, output dan error dari BASH Scripting.

#### 3.2.7 Perulangan (Looping)

Looping adalah konstruksi yang berfungsi untuk memungkinkan mengulangi prosedur atau melakukan prosedur yang sama pada beberapa item yang berbeda. Dalam BASH terdapat pula konstruksi perulangan, perulangan yang digunakan adalah `for` dan `while`. Contoh script dari looping adalah:

```bash
#FOR
for namaVariabel in String1 String2 StringN
do
    instruksi yang dijalankan;
done

#WHILE
while [kondisi]
do
    instruksi yang dijalankan;
done
```

#### 3.2.8 Array

Array adalah sebuah variable yang bisa menyimpan banyak data dalam satu variable. Array dapat menggunakan indeks untuk memudahkan akses terhadap data yang disimpannya. BASH Scripting memiliki fitur yang dapat membaca berbagai tipe pemrograman termasuk array.

## IV. Lab Praktik

### 4.1 Remote menggunakan SSH antara Windows (Host) dengan Rocky Linux (Guest)

#### 4.1.1 Konfigurasi Main OS (Host)

| OS | IP Address | Subnet Mask |
|---|---|---|
| Windows | 10.10.80.2 | 255.255.255.128 |
| Rocky Linux | 10.10.80.1 | 255.255.255.128 |

1. Pertama-tama, lakukan konfigurasi IP Address pada Main OS dengan cara melakukan pencarian pada Windows dan masuk ke *Control Panel*.
2. Pada Control Panel yang baru terbuka, pilih *Network and Internet*.
3. Pada Network dan Internet, pilih *Network and Sharing Center*.
4. Pada Network and Sharing Center, pilih *Change adapter settings*.
5. Setelah itu akan ditampilkan beberapa network adapters yang tersedia, pilih network adapters yang memiliki status Host-only yang berhubungan dengan Rocky Linux pada VMware Workstation. Pada contoh berikut ini, klik dua kali pada *VMware Network Adapter VMnet1*.
6. Pada jendela *VMware Network Adapter VMnet1 Status* yang baru terbuka, pilih *Properties*.
7. Pada jendela *VMware Network Adapter VMnet1 Properties* yang baru terbuka, pilih *Internet Protocol Version 4 (TCP/IPv4)* lalu klik *Properties*.
8. Pilih *Use the following IP Address*, lalu masukkan IP Address dan Subnet mask sesuai dengan tabel IP yang tersedia (Windows: `10.10.80.2` / `255.255.255.128`). Jika sudah selesai klik OK dan klik OK kembali pada jendela Adapter Properties.

#### 4.1.2 Konfigurasi Virtual Machine (Guest)

1. Buka Virtual Machine, kemudian klik *Edit* pada bagian Tab. Setelah itu, klik bagian *Virtual Network Editor*.
2. Pada tampilan Virtual Network Editor, klik *Change Settings*.
3. Selanjutnya, pilih *VMNet1*. Kemudian uncheck "Use local DHCP service to distribute IP address to VMs". Setelah itu sesuaikan Subnet IP dan Subnet mask sesuai dengan gambar pada modul (jaringan 10.10.80.x dengan mask `255.255.255.128`, sesuai tabel IP).
4. Klik Apply kemudian OK.
5. Pada tampilan Virtual Machine, klik *Edit virtual machine settings*. Setelah itu klik *Add*.
6. Selanjutnya, pilih *Network Adapter* dan klik Finish.
7. Pada *Network Adapter 2*, pilih Network connection *Custom: Specific virtual network*. Klik dropdown, kemudian pilih *VMNet1 (Host-only)*. Setelah itu, klik OK.
8. Nyalakan virtual machine dan buka terminal Rocky Linux dan login sebagai root, ini berfungsi untuk mendapatkan akses tertinggi pada sistem operasi Linux dan bisa melakukan pekerjaan tanpa dibatasi oleh sistem yang ada.
9. Lakukan pengecekan port SSH. Setelah dilakukan pengecekan, hapus tanda `#` pada `Port 22`.

```bash
[root@localhost sisjarlab]# nano /etc/ssh/sshd_config
```

10. Kemudian, pada NMTUI kita melakukan penambahan Ethernet dengan klik *Add*. Pada *New Connection* pilih *Ethernet* dan klik Enter.
11. Pada *Edit Connection*, ketik `ens37` pada bagian Profile name dan Device. Setelah itu klik OK.
12. Selanjutnya kita akan melakukan edit connection pada `ens37` yang telah dibuat. Pilih `ens37` dan gunakan tombol right arrow untuk memilih `<Edit...>`. Tekan Enter.
13. Kita lakukan konfigurasi `ens37` dengan memilih `<Manual>` pada IPv4 Configuration. Kemudian samakan konfigurasi dengan gambar di bawah ini:

```text
Profile name : ens37
Device       : ens37
IPv4 CONFIGURATION <Manual>
  Addresses   : 10.10.80.1/25
  Gateway     : 10.10.80.1
  DNS servers : 10.10.80.1
```

14. Pilih `<OK>` jika sudah selesai konfigurasi.
15. Lakukan pengembalian konfigurasi `ens33` menjadi seperti semula. Klik pada *Addresses* dan *DNS servers*, kemudian jadikan IPv4 Configuration menjadi `<Automatic>`.
16. Klik `<OK>`.
17. Lakukan konfigurasi IP Address pada Rocky Linux dan restart network yang dikonfigurasi untuk melakukan penetapan perubahan IP Address.

```bash
[root@sisjarlab sisjarlab]# systemctl restart NetworkManager
[root@sisjarlab sisjarlab]# reboot
```

18. Pastikan IP Address telah sesuai dengan konfigurasi yang ada.

```bash
[root@sisjarlab sisjarlab]# ifconfig ens37
```

```text
ens37: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
        inet 10.10.80.1  netmask 255.255.255.128  broadcast 10.10.80.127
```

19. Lakukan tes konektivitas dengan perintah `ping` untuk mengecek konektivitas antara:
    a. Windows ke Rocky Linux
    b. Rocky Linux ke Windows. Pastikan firewall pada Windows mati.
20. Buka aplikasi PuTTY untuk melakukan remote SSH dengan port 22, serta masukkan IP Address Rocky Linux pada kolom IP. Jika muncul pemberitahuan security alerts pilih YES.
21. Hasilnya remote berhasil, masukkan username dan password dari user Rocky Linux. Jika berhasil maka komputer/laptop host akan meminta akses ke Rocky Linux, dimana Rocky Linux bertindak sebagai server yang akan di-remote.

### 4.2 Konfigurasi Remote Access SSH dengan Port yang Berbeda

#### 4.2.1 Konfigurasi Firewall dan SELinux

1. Sebelum melakukan perubahan port SSH, lakukan konfigurasi untuk menghentikan serta menonaktifkan firewall melalui CLI.

```bash
[root@localhost sisjarlab] # systemctl stop firewalld
[root@localhost sisjarlab] # systemctl disable firewalld
[root@localhost sisjarlab] # systemctl status firewalld
```

2. Matikan konfigurasi SELinux

```bash
[root@sisjarlab sisjarlab] # nano /etc/selinux/config
```

Ubah baris `SELINUX=` pada file tersebut. Pada modul tertulis:

```text
SELINUX=disable
```

> Catatan: nilai yang valid untuk SELinux adalah `enforcing`, `permissive`, atau `disabled` (dengan huruf "d" di akhir). Gunakan `SELINUX=disabled` jika `disable` tidak berpengaruh.

3. Restart VM Rocky Linux untuk melakukan update konfigurasi firewall serta SELinux

```bash
[root@sisjarlab sisjarlab] # shutdown -r now
```

#### 4.2.2 Mengubah Port Remote Access SSH

Dapat dilakukan dengan menggunakan PuTTY atau terminal pada VM

1. Setelah VM Rocky Linux hidup kembali, masuk ke dalam terminal dan login sebagai root, lalu buka file SSH.

```bash
[root@sisjarlab sisjarlab] # nano -c /etc/ssh/sshd_config
```

2. Hapus tanda `#` pada line ke-17, lalu ubah `Port 22` menjadi `Port 900`

```text
Port 900
```

#### 4.2.3 Memberikan Banner pada Remote Access SSH

- Masih pada file konfigurasi SSH, hapus tanda `#` pada line ke-129 serta ubah konfigurasinya menjadi `Banner /etc/issue.net`.

```bash
[root@sisjarlab sisjarlab] # nano /etc/ssh/sshd_config
```

```text
Banner /etc/issue.net
```

- Buka file `/etc/issue.net` untuk mengkonfigurasi banner sesuai keinginan dengan perintah:

```bash
[root@sisjarlab sisjarlab] # nano /etc/issue.net
```

#### 4.2.4 Konfirmasi dan Menjalankan Perubahan Konfigurasi Remote Access

1. Restart service SSH untuk menetapkan semua perubahan konfigurasi remote access SSH yang sudah dilakukan

```bash
[root@sisjarlab sisjarlab] # systemctl restart sshd
```

2. Buka kembali aplikasi PuTTY untuk melakukan remote SSH pada Port 900, serta masukkan IP Address Rocky Linux.
3. Maka hasilnya, sistem akan berhasil melakukan remote menggunakan port 900. Lalu lakukan login sebagai user, maka akan muncul banner pemberitahuan remote access yang sudah dibuat sebelumnya.
4. Buktikan bahwa port 900 telah mendapatkan hak untuk melakukan remote access

```bash
[root@sisjarlab sisjarlab] $ netstat -tulpn | grep :900
```

### 4.3 BASH Scripting

Langkah 4.3 dilakukan melalui remote access dan lanjutkan dengan mengerjakan langkah berikut:

#### 4.3.1 Operasi Aritmatika Sederhana (Let)

a. Buat file script bernama `hitungansederhanaLet.sh`

```bash
[root@sisjarlab sisjarlab] # nano hitungansederhanaLet.sh
```

b. Isi file dengan script di bawah ini

```bash
#! /bin/bash
#Operasi Hitungan Sederhana menggunakan perintah LET

echo "Masukkan Angka Pertama: "
read angka1
echo "Masukkan Angka Kedua: "
read angka2

let tambah=$angka1+$angka2
let kurang=$angka1-$angka2
let kali=$angka1*$angka2
let bagi=$angka1/$angka2

echo "Maka Hasil Dari Penjumlahan $angka1 + $angka2  adalah" : $tambah
echo "Maka Hasil Dari Pengurangan $angka1 - $angka2 adalah" : $kurang
echo "Maka Hasil Dari Perkalian $angka1 x $angka2 adalah" : : $kali
echo "Maka Hasil Dari Pembagian $angka1 : $angka2 adalah" : $bagi
```

c. Setelah membuat script, atur permission dan jalankan script yang telah dibuat

```bash
[root@sisjarlab sisjarlab] # chmod +x hitungansederhanaLet.sh
[root@sisjarlab sisjarlab] # ./hitungansederhanaLet.sh
```

d. Masukkan angka pertama : 6
e. Masukkan angka kedua : 3
f. Maka hasilnya akan menjadi :

- Hasil Penjumlahan : 9
- Hasil Pengurangan : 3
- Hasil Perkalian : 18
- Hasil Pembagian : 2

#### 4.3.2 Membuat Hitung Mundur

a. Buat file script bernama `count.sh`

```bash
[root@sisjarlab sisjarlab] # nano count.sh
```

b. Isi file dengan script di bawah ini

```bash
#!/bin/bash

COUNT=15

while [ $COUNT -ge 0 ]; do

        echo value of count $COUNT
        let COUNT=COUNT-1

done
```

c. Setelah membuat script, atur permission dan jalankan script yang telah dibuat

```bash
[root@sisjarlab sisjarlab] # chmod +x count.sh
[root@sisjarlab sisjarlab] # ./count.sh
```

Hasilnya mencetak `value of count 15` sampai `value of count 0`.

#### 4.3.3 Membuat Perhitungan Array

a. Buat file script bernama `array.sh`

```bash
[root@sisjarlab sisjarlab] # nano array.sh
```

b. Isi file dengan script di bawah ini

```bash
#!/bin/bash
#Menghitung Jumlah Karakter Pertama pada Array
#Isi Array

declare panjangArray
echo "Panjang Array: "
read panjangArray

declare -a array
i=0
while [ $i -lt $panjangArray ]
        do
        echo "Masukkan Isi Array: "
        read -a arrayX

        array[$i]=$arrayX
        let i=$i+1
done

echo ${array[*]}
```

c. Setelah membuat script, atur permission dan jalankan script yang telah dibuat

```bash
[root@sisjarlab sisjarlab] # chmod +x array.sh
[root@sisjarlab sisjarlab] # ./array.sh
```

d. Pada Panjang array, tuliskan panjang kata yang ingin ditampilkan

e. Masukkan isi Array sesuai dengan keinginan sehingga membentuk kata-kata

Contoh hasil (panjang array 5, isi P, A, H, A, M):

```text
Panjang Array:
5
Masukkan Isi Array:
P
...
P A H A M
```

#### 4.3.4 Mengecek Suatu Direktori

a. Buat file script bernama `directory.sh`

```bash
[root@sisjarlab sisjarlab] # nano directory.sh
```

b. Isi file dengan script di bawah ini

```bash
#!/bin/bash

directory="./BashScripting"

# bash check if directory exists

if [ -d $directory ]; then

        echo "Directory Exists"
else
        echo "Directory doesn't Exists"
        mkdir BashScripting
        mkdir BashScripting/Jurnal
        mkdir BashScripting/Audit
        echo "Directory is Created"
fi
```

c. Setelah membuat script, atur permission dan jalankan script yang telah dibuat.

```bash
[root@sisjarlab sisjarlab] # chmod +x directory.sh
[root@sisjarlab sisjarlab] # ./directory.sh
```

d. Apabila script ini belum pernah dijalankan, maka hasil yang keluar adalah "Directory doesn't Exists" dan script akan menjalankan perintah untuk membuat direktori "BashScripting". Kemudian, jalankan script `directory.sh` sekali lagi. Hasil yang didapatkan akan menjadi "Directory Exists"

e. Lakukan Take Snapshot sebagai backup jika mengalami kendala untuk modul selanjutnya.

## V. Daftar Pustaka

1. Laboratorium Sistem Operasi dan Jaringan Komputer. (2015). *Modul Praktikum Sistem Operasi 2015*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
2. Laboratorium Sistem Operasi dan Jaringan Komputer. (2015). *Modul Praktikum Sistem Operasi 2016*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
3. Laboratorium Sistem Operasi dan Jaringan Komputer. (2015). *Modul Praktikum Sistem Operasi 2019*. Bandung, Laboratorium Sistem Operasi dan Jaringan Komputer.
4. Mallet, A. (2014). *CentOS System Administration Essentials*. Birmingham: Packt Publishing Ltd.
5. Smith, Roderick W. (2009). *CompTIA Linux+ Study Guide*. Indianapolis: Wiley Publishing, Inc.

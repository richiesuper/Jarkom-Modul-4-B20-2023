# Jarkom-Modul-4-B20-2023

Praktikum 4 Jarkom oleh Kelompok B20 (Richie Seputro dan Dimas Aria Pujangga)

# Topologi

![topologi](assets/topologi.png)

# Subnets

![rute](assets/rute.png)

![rute gambar](assets/rute-gambar.png)

# VLSM Subnetting di Cisco Packet Tracer

VLSM adalah teknik subnetting di mana dilakukan pembagian IP kepada host dan subnet jaringan secara variabel dan efisien, sehingga pemborosan IP address dapat diminimalisir. Pada teknik ini, sebuah main net akan dipecah-pecah menjadi 2 subnet yang lebih kecil yang netmask-nya lebih besar 1 dari netmask miliknya sendiri. Misal, main net dengan netmask /24 akan dipecah jadi 2 subnet dengan netmask /25. Teknik ini memanglah lebih efisien dibanding teknik CIDR, namun, bila terjadi penambahan subnet baru / host-host baru, kemungkinan besar perlu dilakukan proses subnetting ulang karena belum tentu skema subnetting yang lama bisa ditambahi dengan host-host / subnet baru tersebut.

Pada teknik VLSM, kita perlu memulai dari main/root network terlebih dahulu, yang mana pada kelompok kami adalah 192.188.0.0/19. Netmask /19 didapatkan dari penghitungan subnet di atas yang memperlihatkan bahwa diperlukan 4255 buah IP address. Perlu diingat juga bahwa pemilihan netmask tidak hanya bergantung dari jumlah IP address yang dibutuhkan, tetapi juga berdasarkan jumlah subnet yang persis di bawahnya. Pada daftar subnet, terlihat bahwa subnet terbesar memerlukan netmask /21. Setelah dilakukan penghitungan, netmask /19 adalah netmask terkecil yang bisa menampung IP address sebanyak itu dan mengakomodir kebutuhan subnet mask subnet-subnet dibawahnya.

## Tree

Berikut adalah tree subnetting VLSM yang didapatkan setelah melakukan proses pemecahan network.

![vlsm tree](assets/vlsm-tree.png)

## Pembagian IP

Berikut adalah tabel pembagian IP dari hasil subnetting VLSM.

![pembagian ip vlsm](assets/vlsm-pembagianIP.png)

# VLSM Routing di Cisco Packet Tracer

Berikut routing table dari masing-masing router

![router](assets/vlsm-aura.png)

![router](assets/vlsm-denken.png)

![router](assets/vlsm-eisen.png)

![router](assets/vlsm-fern.png)

![router](assets/vlsm-flamme.png)

![router](assets/vlsm-frieren.png)

![router](assets/vlsm-heiter.png)

![router](assets/vlsm-himmel.png)

![router](assets/vlsm-lawine.png)

![router](assets/vlsm-linie.png)

![router](assets/vlsm-lugner.png)

# CIDR Subnetting di GNS 3

CIDR (Classless Inter-Domain Routing) adalah metode pengalamatan IP yang menggantikan metode pengalamatan kelas tradisional dalam protokol IPv4. CIDR memungkinkan pembagian subnet secara fleksibel dalam IPv4, yang membantu dalam penggunaan alamat IP yang efisien dan pengelompokan jaringan yang lebih baik.

Sebelum CIDR, alamat IP dibagi menjadi kelas A, B, dan C. Kelas A memiliki 8 bit pengidentifikasi jaringan dan 24 bit pengidentifikasi host, kelas B memiliki 16 bit pengidentifikasi jaringan dan 16 bit pengidentifikasi host, dan kelas C memiliki 24 bit pengidentifikasi jaringan dan 8 bit pengidentifikasi host.

Sistem pengalamatan kelas ini memiliki beberapa kelemahan. Misalnya, kelas A dapat mendukung hingga 16 juta host, tetapi banyak organisasi tidak memerlukan jumlah host sebanyak itu. Akibatnya, sebagian besar alamat kelas A tidak digunakan.

CIDR mengatasi kelemahan ini dengan memungkinkan organisasi untuk mengalokasikan jumlah bit pengidentifikasi jaringan yang mereka butuhkan. Misalnya, organisasi dengan 100 host dapat mengalokasikan 16 bit pengidentifikasi jaringan, yang memungkinkan mereka untuk menggunakan alamat kelas C.

Notasi CIDR digunakan untuk mewakili alamat IP dan jumlah bit pengidentifikasi jaringan. Notasi ini terdiri dari alamat IP diikuti oleh tanda garis miring (/) dan jumlah bit pengidentifikasi jaringan. Misalnya, alamat IP 192.168.1.0 dengan 22 bit pengidentifikasi jaringan direpresentasikan sebagai 192.168.1.0/22.

## Penggabungan Node

![penggabunganIP](assets/penggabunganIP.png)

![penggabunganIP](assets/penggabunganIP(1).png)

![penggabunganIP](assets/penggabunganIP(2).png)

## Tree

Setelah dilakukannya penggabungan IP, sekarang kita melakukan pembagian IP dengan menggunakan tree pada masing-masing kelompok yang telah dibuat sebelumnya sebagai berikut.

![Tree](assets/tree.png)

## Pembagian IP

Berikut merupakan hasil dari pembagian IP berdasarkan Tree yang telah dibuat sebelumnya.

![PembagianIP](assets/pembagianIP.png)

## CIDR Routing di GNS 3

Untuk menguji keberhasilan konfigurasi routing, dalam GNS3 dapat dilakukan pengujian menggunakan perintah traceroute. Sebagai contoh, pada device AppetitRegion, dilakukan traceroute ke device GranzChannel yang memiliki alamat IP `192.190.224.2.` Proses ini dapat dijalankan dengan perintah `traceroute 192.190.224.`2 pada device AppetitRegion, yang akan menghasilkan output:

![routing](assets/routing.png)
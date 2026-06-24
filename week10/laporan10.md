# Laporan Praktikum Jaringan Komputer IF-04-02
NAMA : Bagas Bintang Saputro
NIM  : 103072400078

## MODUL 10 IP
Tujuan : Mahasiswa dapat menginvestigasi cara kerja protokol IP menggunakan Wireshark

## Menangkap paket dari eksekusi traceroute >tracert gaia.cs.umass.edu
![](../assets/week10/1.png)
![](../assets/week10/2.png)
![](../assets/week10/3.png)

## IPv4 Dasar
## TTL 1 :
![](../assets/week10/4.png)
## TTL 2 :
![](../assets/week10/5.png)
Pada hasil capture Wireshark, terlihat bahwa komputer mengirim ICMP Echo Request dengan nilai TTL = 1 ke tujuan 128.119.245.12. Router pertama kemudian mengurangi nilai TTL menjadi 0 dan mengirimkan balasan ICMP “Time-To-Live Exceeded”. Hal ini menunjukkan bahwa traceroute berhasil mengidentifikasi hop pertama dalam jaringan.
## Fregmentasi
![](../assets/week10/6.png)
Pada hasil analisis ditemukan fragmentasi IP. Hal ini ditunjukkan oleh adanya paket dengan nilai Fragment Offset lebih dari 0, yaitu sebesar 1480. Selain itu, nilai More Fragments (MF) pada paket tersebut adalah 0, yang menunjukkan bahwa paket tersebut merupakan fragment terakhir. Fragmentasi terjadi karena datagram yang dikirim melebihi ukuran Maximum Transmission Unit (MTU), sehingga dipecah menjadi beberapa bagian. Hal ini diperkuat dengan adanya beberapa paket yang memiliki nilai Identification yang sama.

## IPv6
Berdasarkan hasil analisis menggunakan Wireshark, ditemukan paket DNS yang berisi permintaan tipe A (IPv4), seperti pada domain youtube.com dan doubleclick.net. Namun, tidak ditemukan paket DNS dengan tipe AAAA (IPv6). Hal ini menunjukkan bahwa pada saat proses capture dilakukan, sistem hanya melakukan resolusi alamat IPv4 dan tidak melakukan permintaan alamat IPv6. Kemungkinan hal ini disebabkan oleh konfigurasi jaringan atau DNS server yang tidak mengutamakan penggunaan IPv6.
![](../assets/week10/7.png)

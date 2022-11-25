
# Jarkom-Modul-4-ITA09-2022
1. Muhammad Alwan 5027201019
2. Rayhan Kurnia Alunantara Wijaya 5027201030


## Topologi
#### CPT
![App Screenshot](https://archive.org/download/modul4/tCPT.png)
#### GNS3
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/tGNS3.png)
## VLSM
#### Subnetting
Selanjutnya kita akan melakukan subnetting dengan metode VLSM pada CPT, kita akan membagi gambar pada
topologi menjadi beberapa bagian menjadi seperti berikut: 
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/Screenshot%202022-11-23%20190624.png)
Lalu kita menetukan netmask berdasarkan jumlah host dari pembagian yang telah dilakukan.

| Nama  | Jumlah Host | Netmask |
| ------------- | ------------- | ------------- | 
| A1 | 1001  | /22  |
| A2  | 251 | /24 |
| A3  | 2  | /30 |
| A4 | 2 | /30 |
| A5  | 151 | /24  |
| A6  | 2  | /30  |
| A7 | 121 | /25 |
| A8  | 211 | /24  |
| A9 | 2  | /30 |
| A10  | 21 | /27  |
| A11  | 2  | /30  |
| A12  | 2  | /30 |
| A13  | 2  | /30  |
| A14  | 501  | /23  |
| A15  | 271  | /23 |
| A16  | 71 | /25 |
| A17  | 121 | /25 |
| A18 | 2  | /30  |
| Total | 2736  | /20 |

Lalu setelah menentukan netmask dan mendapatkan network berada pada netmask /20, kita 
membuat pembagian IP dengan prefix 10.44.x.x untuk kelompok kami dengan menggunakan VLSM tree sebagai berikut:
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/VLSM_TREE.png)

Berdasarkan VLSM tree diatas dapat dibuat table menjadi seperti diabawah:
|Nama|Host diperlukan|Host dialokasikan|Network Address|Mask|Netmask|Range IP tersedia|Broadcast|
|-|-|-|-|-|-|-|-|
|A1|1001|1022|10.44.0.0|/22|255.255.252.0|10.44.0.1 - 10.44.3.254|10.44.3.255|
|A14|501|510|10.44.4.0|/23|255.255.254.0|10.44.4.1 - 10.44.5.254|10.44.5.255|
|A15|271|510|10.44.6.0|/23|255.255.254.0|10.44.6.1 - 10.44.7.254|10.44.7.255|
|A1|251|254|10.44.8.0|/24|255.255.255.0|10.44.8.1 - 10.44.8.254|10.44.8.255|
|A8|211|254|10.44.9.0|/24|255.255.255.0|10.44.9.1 - 10.44.9.254|10.44.9.255|
|A5A|151|254|10.44.10.0|/24|255.255.255.0|10.44.10.1 - 10.44.10.254|10.44.10.255|
|A7|121|126|10.44.11.0|/25|255.255.255.128|10.44.11.1 - 10.44.11.126|10.44.11.127|
|A17|121|126|10.44.11.128|/25|255.255.255.128|10.44.11.129 - 10.44.11.254|10.44.11.255|
|A16|71|126|10.44.12.0|/25|255.255.255.128|10.44.12.1 - 10.44.12.126|10.44.12.127|
|A10|21|30|10.44.12.128|/27|255.255.255.224|10.44.12.129 - 10.44.12.158|10.44.12.159|
|A3|2|2|10.44.12.160|/30|255.255.255.252|10.44.12.161 - 10.44.12.162|10.44.12.163|
|A4|2|2|10.44.12.164|/30|255.255.255.252|10.44.12.165 - 10.44.12.166|10.44.12.167|
|A6|2|2|10.44.12.168|/30|255.255.255.252|10.44.12.169 - 10.44.12.170|10.44.12.171|
|A9|2|2|10.44.12.172|/30|255.255.255.252|10.44.12.173 - 10.44.12.174|10.44.12.175|
|A11|2|2|10.44.12.176|/30|255.255.255.252|10.44.12.177 - 10.44.12.178|10.44.12.179|
|A12|2|2|10.44.12.180|/30|255.255.255.252|10.44.12.181 - 10.44.12.182|10.44.12.183|
|A13|2|2|10.44.12.184|/30|255.255.255.252|10.44.12.185 - 10.44.12.186|10.44.12.187|
|A18|2|2|10.44.12.188|/30|255.255.255.252|10.44.12.189 - 10.44.12.190|10.44.12.191|

Lalu kita akan mengatur IP pada setiap node yang ada pada setiap pembagian VLSM dari A1-A18
contohnya sebagai berikut untuk subnet A1:
```
Subnet A1 : 
    NID : 10.44.0.0
    Netmask : 255.255.252.0
    IP range : 10.44.0.1 - 10.44.3.254
```
Selanjutnya kita atur pada setiap node, contohnya pada node The Order yang terhubung pada A1 adalah
kabel FastEthernernet0/0, maka kita ubah interface The Minister menjadi seperti berikut:
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/The%20Minister%2011_25_2022%201_25_54%20PM.png)

Selanjutnya kita atur gateway pada client A1 yaitu Guideau seperti berikut:
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/Guideau%20%281000%20Host%29%2011_25_2022%201_29_06%20PM.png)

Selanjutnya kita akan mengatur IP pada setiap client yang ada sesuai dengan range IP yang tersedia, contohnya pada client A1 kita atur IP
Guideau menjadi 10.44.0.2 karena 10.44.0.1 telah dipakai oleh router.
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/Guideau%20%281000%20Host%29%2011_25_2022%201_29_19%20PM.png)

Langkah tersebut dilakukan untuk semua router dan client yang ada sesuai pembagian subnetting.

#### Subnetting
Setelah semua router dan client kita atur dan berikan IP yang sesuai dengan subnetting, selanjutnya kita
akan melakukan routing untuk menghubungkan semua node.
Contohnya pada router The Minister.

- Terhubung dengan A2
- Berada dibawah router The Order

Pengaturan routing untuk The Minister berdasarkan data diatas adalah:
```
Subnet A2 :
    NID = 10.44.8.0
    Netmask = 255.255.255.0
    NextHop  = 10.44.12.165

Routing karena dibawah router The Order
    NID : 0.0.0.0
    Netmask : 0.0.0.0
    Nexthop : 10.44.12.162
```
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/The%20Minister%2011_25_2022%201_43_59%20PM.png)

Berikut pengaturan routing setiap router:

- The Minister
```
0.0.0.0/0 via 10.44.12.165
10.44.8.0/24 via 10.44.12.162
```
- The Order
```
0.0.0.0/0 via 10.44.12.169
10.44.0.0/22 via 10.44.12.166
10.44.8.0/24 via 10.44.12.166
```
- The Resonance
```
10.44.10.0/24 via 10.44.12.170
10.44.12.164/30 via 10.44.12.170
10.44.0.0/22 via 10.44.12.170
10.44.12.160/30 via 10.44.12.170
10.44.8.0/24 via 10.44.12.170
10.44.6.0/23 via 10.44.12.178
10.44.11.0/25 via 10.44.12.182
10.44.12.188/30 via 10.44.12.182
10.44.11.128/25 via 10.44.12.182
10.44.12.0/25 via 10.44.12.182
10.44.12.184/30 via 10.44.12.182
10.44.4.0/23 via 10.44.12.182
10.44.9.0/24 via 10.44.12.182
10.44.12.172/30 via 10.44.12.182
```
- The Magical
```
0.0.0.0/0 via 10.44.12.177
```
- The Instrument
```
0.0.0.0/0 via 10.44.12.181
10.44.11.128/25 via 10.44.12.190
10.44.4.0/23 via 10.44.12.186
10.44.9.0/24 via 10.44.12.186
10.44.12.172/30 via 10.44.12.186
```
- The Firefist
```
0.0.0.0/0 via 10.44.12.185
10.44.12.172/30 via 10.44.9.3
```
- The Queen
```
0.0.0.0/0 via 10.44.9.1
```
- The Profound
```
0.0.0.0/0 via 10.44.12.189
```
- The Dauntless
```
0.0.0.0/0 via 10.44.12.161
```

Setelah semua routing dilakukan, maka client sudah terhubung dengan client lain.

#### Testing

Kita akan coba melakukan testing mengirim pesan dari client Guideau ke client Johan dan berhasil terkirim:
![App Screenshot](https://archive.org/download/cisco-packet-tracer-c-users-lenovo-one-drive-dokumen-t-3-mp-jkm-mod-4-jarkom-mod/Cisco%20Packet%20Tracer%20-%20C__Users_lenovo_OneDrive_Dokumen_T3MP_JKM_mod4_JARKOM-MODUL-4-ITA09-2022.pkt%2011_25_2022%201_52_39%20PM.png)


# Jarkom-Modul-2-B25-2023

## Nama Anggota :
1. Muhamad Faiz Fernanda (5025211186)

## Topologi

![Screenshot 2023-10-17 013741](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/a5c5edb2-3434-4571-9b7e-6b6c10940e26)

## Network Configuration
- #### Pandudewanata
```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.21.1.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.21.2.1
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.21.3.1
```
- #### Yudhistira
```
auto eth0
iface eth0 inet static
	address 10.21.1.2
	netmask 255.255.255.0
	gateway 10.21.1.1
```
- ####  Nakula
  ```
  auto eth0
  iface eth0 inet static
	address 10.21.1.3
	netmask 255.255.255.0
	gateway 10.21.1.1
  ```
- #### Werkudara
  ```
  auto eth0
  iface eth0 inet static
	    address 10.21.2.2
	    netmask 255.255.255.0
	    gateway 10.21.2.1
  ```
- #### Sadewa
```
  auto eth0
iface eth0 inet static
	address 10.21.2.3
	netmask 255.255.255.0
	gateway 10.21.2.1

  ```
- #### Arjuna
```
 auto eth0
 iface eth0 inet static
	    address 10.21.3.2
	    netmask 255.255.255.0
	    gateway 10.21.3.1
  ```
- #### Prabukusuma
```
  auto eth0
  iface eth0 inet static
	    address 10.21.3.3
	    netmask 255.255.255.0
	    gateway 10.21.3.1
  ```
- #### Abimanyu
```
auto eth0
iface eth0 inet static
	address 10.21.3.4
	netmask 255.255.255.0
	gateway 10.21.3.1

  ```
- #### Wisanggenni
```
auto eth0
iface eth0 inet static
	address 10.21.3.5
	netmask 255.255.255.0
	gateway 10.21.3.1

  ```
## Pemabahasan Soal
### 2. Buatlah website utama pada node arjuna dengan akses ke arjuna.yyy.com dengan alias www.arjuna.yyy.com dengan yyy merupakan kode kelompok
#### Solusi 
- Melakukan configurasi pada dns master yaitu pada server Yudhistira

![Screenshot 2023-10-17 015212](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/0f7a6384-ccb8-4380-aeb2-87fe037681c2)
- Membuat folder arjuna di dalam /etc/bind

![Screenshot 2023-10-17 015222](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b4abf8e3-d22c-48a6-8ca7-fa52622d180c)
- Copykan file db.local pada path /etc/bind ke dalam folder arjuna  yang baru saja dibuat dan ubah namanya menjadi arjuna.B25.com

![Screenshot 2023-10-17 015237](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/4e185d7e-a682-4c84-9be3-5cf5de843b13)
- Melakukan set up pada file arjuna.B25.com sesuai gambar berikut :
  ![Screenshot 2023-10-17 020316](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/9bfc150a-023e-4227-bc9f-90f4d7524788)

- lalu melakukan restart bind9
  
![Screenshot 2023-10-17 015712](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/62caf689-1538-4fe4-a6a5-6c0ca7af5adb)
- Bukti yaitu dapat di lakukan ping arjuna.B25.com
  
![Screenshot 2023-10-17 015803](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/7b82fa6f-2706-4fc5-b4cf-18f14f0a5e69)

### 3. Dengan cara yang sama seperti soal nomor 2, buatlah website utama dengan akses ke abimanyu.yyy.com dan alias www.abimanyu.yyy.com.
#### Solusi 
- Melakukan configurasi pada dns master yaitu pada server Yudhistira

![Screenshot 2023-10-17 015928](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/591b269e-1a79-4c80-9ce2-2f6b918d4d40)
- Membuat folder abimanyu di dalam /etc/bind

![Screenshot 2023-10-17 015943](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/3396c9cf-81e1-452e-8fca-e5ed16f153d0)
- Copykan file db.local pada path /etc/bind ke dalam folder abimanyu  yang baru saja dibuat dan ubah namanya menjadi abimanyu.B25.com

![Screenshot 2023-10-17 015955](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/6d1c963e-fa43-4f73-8d9c-66c4b0435c45)
- Melakukan set up pada file abimanyu.B25.com sesuai gambar berikut:

![Screenshot 2023-10-17 015428](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/51e0d4ed-d92e-477f-9a46-7cd4271e3e81)
- lalu melakukan restart bind9
  ![Screenshot 2023-10-17 015712](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/3e71d230-4854-4a39-bce3-399853f9bba3)
- Bukti yaitu dapat di lakukan ping abimanyu.B25.com
  ![Screenshot 2023-10-17 020500](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/04aec149-105e-4d7a-af7d-7ed0c6b1f10a)
### 4. Kemudian, karena terdapat beberapa web yang harus di-deploy, buatlah subdomain parikesit.abimanyu.yyy.com yang diatur DNS-nya di Yudhistira dan mengarah ke Abimanyu.
#### Solusi 
- Melakukan kofigurasi pada file abimanyu.B25.com
![Screenshot 2023-10-17 020828](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/6b360354-fb66-461d-b18c-e3f4158155a9)
- Berikut ini saya coba melakukan ping parikesit.abimanyu.B25.com dalam salah satu server yaitu nakula
![Screenshot 2023-10-17 020904](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/672bb0e9-b2ac-479f-8076-07ed119da017)
### 5. Buat juga reverse domain untuk domain utama. (Abimanyu saja yang direverse)
#### Solusi 
- Edit file /etc/bind/named.conf.local pada yudhistira
![Screenshot 2023-10-17 021044](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b78dfaab-dcab-407e-b16c-6c540d985b58)
- Copykan file db.local pada path /etc/bind ke dalam folder abimanyu yang baru saja dibuat dan ubah namanya menjadi 3.21.10.in-addr.arpa
![Screenshot 2023-10-17 021147](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b289f21d-2c9c-4e23-a44a-26df6bb51752)
- Edit file 3.21.10.in-addr.arpa menjadi seperti gambar di bawah ini
![Screenshot 2023-10-17 021325](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/9f8999b6-ea90-4065-bd95-a26352d677aa)

- Kemudian restart bind9
- Untuk mengecek apakah konfigurasi sudah benar atau belum, lakukan perintah berikut pada client nakula
  ![Screenshot 2023-10-17 021441](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/5be3330c-2ee4-43fa-b000-698544755eba)
### 6. Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.
#### Solusi 
- melakukan configuran pada /etc/bind/named.conf.local pada yudhistira sebagai DNS MASTER
##### Untuk Arjuna
![Screenshot 2023-10-17 021652](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/2fae086e-7fce-49bf-8ffb-e226077f3170)
##### Untuk Abimanyu

![Screenshot 2023-10-17 021720](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/6e279c08-02f6-4dbc-94be-c346ac940ccf)



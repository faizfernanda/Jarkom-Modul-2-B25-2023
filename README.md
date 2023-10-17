
## Nama Anggota :
| No | Nama| NRP|
| ------- | ------- | ------- |
| 1 | Muhamad Faiz Fernanda | 5025211186|
| Baris 2 | Nilai C | Nilai D |


## Topologi

![Screenshot 2023-10-17 013741](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/a5c5edb2-3434-4571-9b7e-6b6c10940e26)

## Daftar Soal
- [Soal 1](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/###-Nomer-1) <br/>
- [Soal 2](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/###-Nomer-2) <br/>

### Nomer 1
### Yudhistira akan digunakan sebagai DNS Master, Werkudara sebagai DNS Slave, Arjuna merupakan Load Balancer yang terdiri dari beberapa Web Server yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Buatlah topologi dengan pembagian sebagai berikut. Folder topologi dapat diakses pada drive berikut. 

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
### Nomer 2
### Buatlah website utama pada node arjuna dengan akses ke arjuna.yyy.com dengan alias www.arjuna.yyy.com dengan yyy merupakan kode kelompok
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
![Screenshot 2023-10-17 032430](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/6904d353-3bfe-4722-b1fc-74e5df27a0e1)

- Edit file /etc/bind/named.conf.local pada yudhistira

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
- Selanjutnya melakukan configurasi pada  /etc/bind/named.conf.local pada werkudara sebagai DNS slave
![Screenshot 2023-10-17 031731](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b68659e8-6ae2-4527-9445-fc8aa35051a6)
- lalu kita menstop blind9 pada yudhistira
- lalu kita uji ping pada server client
![Screenshot 2023-10-17 031818](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/690b44b0-611e-4f6b-b5db-2a808e7c285b)
### 7. Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.
#### Solusi 
- Pada node Yudhistira, buka /etc/bind/abimanyu/abimanyu.B25.com lalu tambahkan script berikut :
![Screenshot 2023-10-17 015428](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/9eb98a00-4123-48ca-bd8f-90d5ffded846)

- Buka /etc/bind/named.conf.options, lalu comment bagian ‘dnssec-validation auto;’, dan tambahkan pada baris berikutnya :
- ![Screenshot 2023-10-17 032148](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/646b2141-b32a-4bce-b319-3351418591cc)

- Selanjutnya, restart server
- Pada node Werkudara, buka /etc/bind/named.conf.local dan edit menjadi berikut
  ![Screenshot 2023-10-17 032357](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/87e5d60f-d046-47d0-a856-53c78c56eac2)

  - Lalu kita membuat folder baru /etc/bind/baratayuda dan membuat sebuah file baratayuda.abimanyu.B25.com dan tambahkan script berikut :
    ![Screenshot 2023-10-17 032817](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b830497f-1ef9-4b9e-ae8d-c82c38c2e3b3)
    - lalu, kita bisa mengetesnya dengan melakukan ping pada domain yang telah diatur sebelumnya melalui  client Nakula :
![Screenshot 2023-10-17 032857](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/d86d7d0f-7c90-41fd-aea9-7ebb9fa0318a)

### 8.Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.
#### Solusi 
- Untuk menambahkan subdomain tersebut, kita hanya menambahkan script /etc/bind/baratayuda.abimanyu.B25.com pada node Werkudara seperti berikut :
![Screenshot 2023-10-17 134946](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/d1d1192f-25b5-4a03-a51b-db0bb1be445d)

- Lalu, kita bisa mengetesnya dengan melakukan ping pada rjp.baratayuda.abimanyu.b25.com melalui client Nakula
  ![Screenshot 2023-10-17 135015](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/e9871d30-060a-4f69-b7ff-6a84e4398909)

### 9. Arjuna merupakan suatu Load Balancer Nginx dengan tiga worker (yang juga menggunakan nginx sebagai webserver) yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Lakukan deployment pada masing-masing worker.
#### Solusi 
##### Script
- jalankan pada node **Prabukusuma**
  ```
  echo nameserver 192.168.122.1 > /etc/resolv.conf
  apt-get update && apt install nginx php php-fpm -y
  php -v
  mkdir /var/www/jarkom
  touch /var/www/jarkom/index.php
  echo ' 
   <?php
	echo "Halo, Kamu berada di Prabukusuma";
   ?>' > /var/www/jarkom/index.php

  cd /etc/nginx/sites-available
  touch /etc/nginx/sites-available/jarkom
  echo '
  server {

 	listen 80;
        #sesuai dengan modul untuk no 10
 	root /var/www/jarkom;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	    include snippets/fastcgi-php.conf;
 	    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
   }' > /etc/nginx/sites-available/jarkom
   
   ln -s /etc/nginx/sites-available/jarkom /etc/nginx/sites-enabled
   rm -rf /etc/nginx/sites-enabled/default
   service php7.0-fpm start
   service nginx restart
   nginx -t

  ```
  - Pada **Wisanggeni**
    ```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update && apt install nginx php php-fpm -y
php -v
mkdir /var/www/jarkom
touch /var/www/jarkom/index.php
echo ' 
<?php
echo "Halo, Kamu berada di Wsanggeni";
?>' > /var/www/jarkom/index.php

cd /etc/nginx/sites-available
touch /etc/nginx/sites-available/jarkom
echo '
server {

 	listen 80;
    #sesuai dengan modul untuk no 10
 	root /var/www/jarkom;

 	index index.php index.html index.htm;
 	server_name _;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	    include snippets/fastcgi-php.conf;
 	    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    	}

    	location ~ /\.ht {
 			deny all;
 	}

 		error_log /var/log/nginx/jarkom_error.log;
 		access_log /var/log/nginx/jarkom_access.log;
	}' > /etc/nginx/sites-available/jarkom
   
ln -s /etc/nginx/sites-available/jarkom /etc/nginx/sites-enabled
rm -rf /etc/nginx/sites-enabled/default
service php7.0-fpm start
service nginx restart
nginx -t
    ```
- Pada **Abimanyu**

```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update && apt install nginx php php-fpm -y
php -v
mkdir /var/www/jarkom
touch /var/www/jarkom/index.php
echo ' 
<?php
echo "Halo, Kamu berada di abimanyu";
?>' > /var/www/jarkom/index.php

cd /etc/nginx/sites-available
touch /etc/nginx/sites-available/jarkom
echo '
server {

 	listen 8002;

 	root /var/www/jarkom;

 	index index.php index.html index.htm;
 	server_name 10.21.3.4;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	    include snippets/fastcgi-php.conf;
 	    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
    }' > /etc/nginx/sites-available/jarkom
   
ln -s /etc/nginx/sites-available/jarkom /etc/nginx/sites-enabled
rm -rf /etc/nginx/sites-enabled/default
service php7.0-fpm start
service nginx restart
nginx -t
```

- Pada **Arjuna** sebagai **Load balancer**
```

Load balancer

echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update && apt install nginx  -y

cd /etc/nginx/sites-available
touch /etc/nginx/sites-available/lb-jarkom
echo '
 # Default menggunakan Round Robin
 upstream myweb  {
 	server 10.21.3.3; #IP prabukusuma
 	server 10.21.3.4; #IP abimanyu
    server 10.21.3.5; #IP wisanggeni
 }

 server {
 	listen 80;
 	server_name arjuna.B25.com;

 	location / {
 	proxy_pass http://myweb;
 	} 
}' > /etc/nginx/sites-available/lb-jarkom
   
ln -s /etc/nginx/sites-available/lb-jarkom /etc/nginx/sites-enabled
service nginx restart
nginx -t

```
- Bukti Ketika udah Berhasil,melakukan lynx pada client server dengan **lynx arjuna.B25.com**


### 10. Kemudian gunakan algoritma Round Robin untuk Load Balancer pada Arjuna. Gunakan server_name pada soal nomor 1. Untuk melakukan pengecekan akses alamat web tersebut kemudian pastikan worker yang digunakan untuk menangani permintaan akan berganti ganti secara acak. Untuk webserver di masing-masing worker wajib berjalan di port 8001-8003. Contoh
   #### - Prabakusuma:8001
   #### - Abimanyu:8002
   #### - Wisanggeni:8003
#### Solusi 
##### Script
- Jalankan script.sh berikut pada **prabukusuma** yaitu mensetting ip pada /etc/nginx/sites-available/jarkom
```

server {

 	listen 8001;
    #sesuai dengan modul untuk no 10
 	root /var/www/jarkom;

 	index index.php index.html index.htm;
 	server_name 10.21.3.3;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	    include snippets/fastcgi-php.conf;
 	    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
}
```
- Jalankan script.sh berikut pada **Wisanggeni** yaitu mensetting ip pada /etc/nginx/sites-available/jarkom
```
server {

 	listen 8003;
    #sesuai dengan modul untuk no 10
 	root /var/www/jarkom;

 	index index.php index.html index.htm;
 	server_name 10.21.3.5;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	    include snippets/fastcgi-php.conf;
 	    fastcgi_pass unix:/var/run/php/php7.0-fpm.sock;
    }

    location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/jarkom_error.log;
 	access_log /var/log/nginx/jarkom_access.log;
}

```


## Nama Anggota :
| No | Nama| NRP|
| ------- | ------- | ------- |
| 1 | Muhamad Faiz Fernanda | 5025211186|
| 2| Tigo S Yoga | 5025211125 |


## Topologi

![Screenshot 2023-10-17 013741](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/a5c5edb2-3434-4571-9b7e-6b6c10940e26)

## Daftar Soal
- [Soal 1](#Nomer-1) <br/>
- [Soal 2](#Nomer-2) <br/>
- [Soal 3](#Nomer-3) <br/>
- [Soal 4](#Nomer-4) <br/>
- [Soal 5](#Nomer-5) <br/>
- [Soal 6](#Nomer-6) <br/>
- [Soal 7](#Nomer-7) <br/>
- [Soal 8](#Nomer-8) <br/>
- [Soal 9](#Nomer-9) <br/>
- [Soal 10](#Nomer-10) <br/>
- [Soal 11](#Nomer-11) <br/>
- [Soal 12](#Nomer-12) <br/>
- [Soal 13](#Nomer-13) <br/>
- [Soal 14](#Nomer-14) <br/>
- [Soal 15](#Nomer-15) <br/>
- [Soal 16](#Nomer-16) <br/>
- [Soal 17](#Nomer-17) <br/>
- [Soal 18](#Nomer-18) <br/>
- [Soal 19](#Nomer-19) <br/>
- [Soal 20](#Nomer-20) <br/>

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

### Nomer 3
### Dengan cara yang sama seperti soal nomor 2, buatlah website utama dengan akses ke abimanyu.yyy.com dan alias www.abimanyu.yyy.com.
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
### Nomer 4
### Kemudian, karena terdapat beberapa web yang harus di-deploy, buatlah subdomain parikesit.abimanyu.yyy.com yang diatur DNS-nya di Yudhistira dan mengarah ke Abimanyu.
#### Solusi 
- Melakukan kofigurasi pada file abimanyu.B25.com
![Screenshot 2023-10-17 020828](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/6b360354-fb66-461d-b18c-e3f4158155a9)
- Berikut ini saya coba melakukan ping parikesit.abimanyu.B25.com dalam salah satu server yaitu nakula
![Screenshot 2023-10-17 020904](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/672bb0e9-b2ac-479f-8076-07ed119da017)
### Nomer 5
### Buat juga reverse domain untuk domain utama. (Abimanyu saja yang direverse)
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
### Nomer 6
### Agar dapat tetap dihubungi ketika DNS Server Yudhistira bermasalah, buat juga Werkudara sebagai DNS Slave untuk domain utama.
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
### Nomer 7
### Seperti yang kita tahu karena banyak sekali informasi yang harus diterima, buatlah subdomain khusus untuk perang yaitu baratayuda.abimanyu.yyy.com dengan alias www.baratayuda.abimanyu.yyy.com yang didelegasikan dari Yudhistira ke Werkudara dengan IP menuju ke Abimanyu dalam folder Baratayuda.
#### Solusi 
- Pada node Yudhistira, buka /etc/bind/abimanyu/abimanyu.B25.com lalu tambahkan script berikut :
![Screenshot 2023-10-17 015428](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/9eb98a00-4123-48ca-bd8f-90d5ffded846)

- Buka /etc/bind/named.conf.options, lalu comment bagian ‘dnssec-validation auto;’, dan tambahkan pada baris berikutnya :
![Screenshot 2023-10-17 032148](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/646b2141-b32a-4bce-b319-3351418591cc)

- Selanjutnya, restart server
- Pada node Werkudara, buka /etc/bind/named.conf.local dan edit menjadi berikut
![Screenshot 2023-10-17 032357](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/87e5d60f-d046-47d0-a856-53c78c56eac2)

  - Lalu kita membuat folder baru /etc/bind/baratayuda dan membuat sebuah file baratayuda.abimanyu.B25.com dan tambahkan script berikut :

![Screenshot 2023-10-17 032817](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/b830497f-1ef9-4b9e-ae8d-c82c38c2e3b3)
    - lalu, kita bisa mengetesnya dengan melakukan ping pada domain yang telah diatur sebelumnya melalui  client Nakula :

![Screenshot 2023-10-17 032857](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/d86d7d0f-7c90-41fd-aea9-7ebb9fa0318a)

### Nomer 8
### Untuk informasi yang lebih spesifik mengenai Ranjapan Baratayuda, buatlah subdomain melalui Werkudara dengan akses rjp.baratayuda.abimanyu.yyy.com dengan alias www.rjp.baratayuda.abimanyu.yyy.com yang mengarah ke Abimanyu.
#### Solusi 
- Untuk menambahkan subdomain tersebut, kita hanya menambahkan script /etc/bind/baratayuda.abimanyu.B25.com pada node Werkudara seperti berikut :

![Screenshot 2023-10-17 134946](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/d1d1192f-25b5-4a03-a51b-db0bb1be445d)

- Lalu, kita bisa mengetesnya dengan melakukan ping pada rjp.baratayuda.abimanyu.b25.com melalui client Nakula

![Screenshot 2023-10-17 135015](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/101172294/e9871d30-060a-4f69-b7ff-6a84e4398909)

### Nomer 9
### Arjuna merupakan suatu Load Balancer Nginx dengan tiga worker (yang juga menggunakan nginx sebagai webserver) yaitu Prabakusuma, Abimanyu, dan Wisanggeni. Lakukan deployment pada masing-masing worker.
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


### Nomer 10
### Kemudian gunakan algoritma Round Robin untuk Load Balancer pada Arjuna. Gunakan server_name pada soal nomor 1. Untuk melakukan pengecekan akses alamat web tersebut kemudian pastikan worker yang digunakan untuk menangani permintaan akan berganti ganti secara acak. Untuk webserver di masing-masing worker wajib berjalan di port 8001-8003. Contoh
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

### Nomer 11
### Selain menggunakan Nginx, lakukan konfigurasi Apache Web Server pada worker Abimanyu dengan web server www.abimanyu.yyy.com. Pertama dibutuhkan web server dengan DocumentRoot pada /var/www/abimanyu.yyy
#### Solusi
- Pertama, install apache, wget untuk download file, unzip untuk unzip, dan  folder pada worker Abimanyu dengan cara ketik command dibawah.
  ```
  apt-get install wget -y 
  apt-get install unzip -y
  apt-get install apache2 -y
  apt-get install libapache2-mod-php7.0
  ```
- Lalu kita download resource yang telah disediakan dan unzip lalu pindahkan
  ```
  wget -O '/var/www/abimanyu.B25.com.zip' 'https://drive.usercontent.google.com/download?id=1a4V23hwK9S7hQEDEcv9FL14UkkrHc-Zc'
  unzip -o /var/www/abimanyu.B25.com.zip -d /var/www/
  mv /var/www/abimanyu.yyy.com /var/www/abimanyu.B25.com
  ```
- Setting /etc/apache2/sites-available/abimanyu.B25.com.conf
  ```
  <VirtualHost *:80>
        ServerName abimanyu.B25.com
        ServerAlias www.abimanyu.B25.com

        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/abimanyu.B25

        <Directory /var/www/abimanyu.B25>
            Options +FollowSymLinks -Multiviews
            AllowOverride All
        </Directory>

        ErrorLog \${APACHE_LOG_DIR}/error.log
        CustomLog \${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>
  ```
- Enable konfigurasi dan restart server apache
  ```
  a2ensite abimanyu.B25.com.conf
  service apache2 restart
  ```
- Testing
  ```
  lynx abimanyu.B25.com
  ```
- Hasil
  
  ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/ed3c41b9-bd0c-41ab-90cd-eeb4b0c46a82)

### Nomer 12
### Setelah itu ubahlah agar url www.abimanyu.yyy.com/index.php/home menjadi www.abimanyu.yyy.com/home.
#### Solusi
- Tambahkan script dibawah pada /var/www/abimanyu.B25/.htaccess
  ```
  RewriteEngine On
  RewriteBase /

  RewriteCond %{REQUEST_FILENAME} !-f
  RewriteCond %{REQUEST_FILENAME} !-d
  RewriteRule ^(.*)$ index.php/$1 [L]
  ```
- Testing
  ```
  lynx abimanyu.B25.com/home
  ```
- Hasil

  ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/03e02ac7-ef0c-476b-87e4-3c88f94c0fff)

### Nomer 13
### Selain itu, pada subdomain www.parikesit.abimanyu.yyy.com, DocumentRoot disimpan pada /var/www/parikesit.abimanyu.yyy
- Download resource yang telah disediakan dan unzip lalu pindahkan
  ```
  wget -O '/var/www/parikesit.abimanyu.B25.com.zip' 'https://drive.usercontent.google.com/download?id=1LdbYntiYVF_NVNgJis1GLCLPEGyIOreS'
  unzip -o /var/www/parikesit.abimanyu.B25.com.zip -d /var/www/
  mv /var/www/parikesit.abimanyu.yyy.com /var/www/parikesit.abimanyu.B25
  ```
- Setting /etc/apache2/sites-available/parikesit.abimanyu.B25.com.conf
  ```
  <VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/parikesit.abimanyu.B26
        ServerName parikesit.abimanyu.B25.com
        ServerAlias www.parikesit.abimanyu.B25.com

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </Virtualhost>
  ```
- Enable konfigurasi dan restart server apache
  ```
  a2ensite parikesit.abimanyu.B25.com
  service apache2 restart
  ```
- Testing
  ```
  lynx parikseit.abimanyu.B25.com
  ```
- Hasil

  ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/550f76e3-192d-4fa9-80b9-5ab1acd16c1d)

### Nomer 14
### Pada subdomain tersebut folder /public hanya dapat melakukan directory listing sedangkan pada folder /secret tidak dapat diakses (403 Forbidden).
#### Solusi
- Buat folder secret
  ```
  mkdir /var/www/parikesit.abimanyu.aB25/secret
  ```
- Setting /etc/apache2/sites-available/parikesit.abimanyu.b25.com.conf
  ```
  <VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/parikesit.abimanyu.B25
        ServerName parikesit.abimanyu.B25.com
        ServerAlias www.parikesit.abimanyu.B25.com

        <Directory /var/www/parikesit.abimanyu.B25/public>
                Options +Indexes
        </Directory>
        <Directory /var/www/parikesit.abimanyu.B25/secret>
                Options -Indexes +FollowSymLinks
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </Virtualhost>
  ```
- Testing
  ```
   lynx parikseit.abimanyu.B25.com/public
  ```

- Hasil

  ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/925bbec0-aa2a-4c2e-bdd1-3e221023cf37)

### Nomer 15
### Buatlah kustomisasi halaman error pada folder /error untuk mengganti error kode pada Apache. Error kode yang perlu diganti adalah 404 Not Found dan 403 Forbidden.
#### Solusi
- Setting /etc/apache2/sites-available/parikesit.abimanyu.B25.com.conf
  ```
  <VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/parikesit.abimanyu.B25
        ServerName parikesit.abimanyu.B25.com
        ServerAlias www.parikesit.abimanyu.B25.com

        <Directory /var/www/parikesit.abimanyu.B25/public>
                Options +Indexes
        </Directory>
        <Directory /var/www/parikesit.abimanyu.B25/secret>
                Options -Indexes +FollowSymLinks
        </Directory>

        ErrorDocument 403 /error/403.html
        ErrorDocument 404 /error/404.html

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </Virtualhost>
  ```
- Testing
  ```
  lynx parikseit.abimanyu.B25.com/js
  ```
- Hasil


### Nomer 16
### Buatlah suatu konfigurasi virtual host agar file asset www.parikesit.abimanyu.yyy.com/public/js menjadi www.parikesit.abimanyu.yyy.com/js
#### Solusi
- Setting /etc/apache2/sites-available/parikesit.abimanyu.B25.com.conf
  ```
  <VirtualHost *:80>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/parikesit.abimanyu.B25
        ServerName parikesit.abimanyu.B25.com
        ServerAlias www.parikesit.abimanyu.B25.com

        <Directory /var/www/parikesit.abimanyu.B25/public>
                Options +Indexes
        </Directory>
        <Directory /var/www/parikesit.abimanyu.B25/secret>
                Options -Indexes +FollowSymLinks
        </Directory>

        ErrorDocument 403 /error/403.html
        ErrorDocument 404 /error/404.html

        Alias "/js" "/var/www/parikesit.abimanyu.B25/public/js"

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </Virtualhost>
  ```
- Testing
  ```
  lynx parikseit.abimanyu.B25.com/js
  ```
- Hasil

 ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/20b2f7c6-c3c5-49df-8a37-fa53911fc95c)

### Nomer 17
### Agar aman, buatlah konfigurasi agar www.rjp.baratayuda.abimanyu.yyy.com hanya dapat diakses melalui port 14000 dan 14400.
#### Solusi
- Download resource yang telah disediakan dan unzip lalu pindahkan
  ```
  wget -O '/var/www/rjp.baratayuda.abimanyu.B25.com.zip' 'https://drive.usercontent.google.com/download?id=1pPSP7yIR05JhSFG67RVzgkb-VcW9vQO6'
  unzip -o /var/www/rjp.baratayuda.abimanyu.B25.com.zip -d /var/www/
  mv /var/www/rjp.baratayuda.abimanyu.yyy.com /var/www/rjp.baratayuda.abimanyu.B25
  ```
- Setting /etc/apache2/sites-available/rjp.baratayuda.abimanyu.B25.com.conf
  ```
  <VirtualHost *:14000>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/rjp.baratayuda.abimanyu.B25
        ServerName rjp.baratayuda.abimanyu.B25.com
        ServerAlias www.rjp.baratayuda.abimanyu.B25.com
        
        <Directory /var/www/rjp.baratayuda.abimanyu.B25>
           AuthType Basic
           AuthName "Restricted Access"
           AuthUserFile /etc/apache2/.htpasswd
           Require valid-user
        </Directory>


        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>

  <VirtualHost *:14400>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/rjp.baratayuda.abimanyu.B25
        ServerName rjp.baratayuda.abimanyu.B25.com
        ServerAlias www.rjp.baratayuda.abimanyu.B25.com
        
        <Directory /var/www/rjp.baratayuda.abimanyu.B25>
           AuthType Basic
           AuthName "Restricted Access"
           AuthUserFile /etc/apache2/.htpasswd
           Require valid-user
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>
  ```
- Setting /etc/apache2/ports.conf
  ```
  Listen 14000
  Listen 14400
  ```
- Testing
  ```
  lynx rjp.baratayuda.abimanyu.B25:14000
  ```
- Hasil

  ![image](https://github.com/faizfernanda/Jarkom-Modul-2-B25-2023/assets/88433109/b58f7022-6a89-4144-8d4a-49e05030c3bb)

  (memerlukan autentikasi karena soal 18)

### Nomer 18
### Untuk mengaksesnya buatlah autentikasi username berupa “Wayang” dan password “baratayudayyy” dengan yyy merupakan kode kelompok. Letakkan DocumentRoot pada /var/www/rjp.baratayuda.abimanyu.yyy.
#### Solusi
- Setting untuk membuat password
  ```
  htpasswd -c /etc/apache2/.htpasswd Wayang
  ```
- Setting /etc/apache2/sites-available/rjp.baratayuda.abimanyu.B25.com.conf
  ```
  <VirtualHost *:14000>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/rjp.baratayuda.abimanyu.B25
        ServerName rjp.baratayuda.abimanyu.B25.com
        ServerAlias www.rjp.baratayuda.abimanyu.B25.com
        
        <Directory /var/www/rjp.baratayuda.abimanyu.B25>
           AuthType Basic
           AuthName "Restricted Access"
           AuthUserFile /etc/apache2/.htpasswd
           Require valid-user
        </Directory>


        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>

  <VirtualHost *:14400>
        ServerAdmin webmaster@localhost
        DocumentRoot /var/www/rjp.baratayuda.abimanyu.B25
        ServerName rjp.baratayuda.abimanyu.B25.com
        ServerAlias www.rjp.baratayuda.abimanyu.B25.com
        
        <Directory /var/www/rjp.baratayuda.abimanyu.B25>
           AuthType Basic
           AuthName "Restricted Access"
           AuthUserFile /etc/apache2/.htpasswd
           Require valid-user
        </Directory>

        ErrorLog ${APACHE_LOG_DIR}/error.log
        CustomLog ${APACHE_LOG_DIR}/access.log combined
  </VirtualHost>
  ```

### Nomer 19
### Buatlah agar setiap kali mengakses IP dari Abimanyu akan secara otomatis dialihkan ke www.abimanyu.yyy.com (alias)
- Setting /etc/nginx/sites-available/jarkom, tambahkan script dibawah pdaa file sebelumnya
 ```
 server {
	listen 8002;
	server_name _;

	return 301 http://www.abimanyu.B25.com;
}
 ```

### Nomer 20
### Karena website www.parikesit.abimanyu.yyy.com semakin banyak pengunjung dan banyak gambar gambar random, maka ubahlah request gambar yang memiliki substring “abimanyu” akan diarahkan menuju abimanyu.png.
#### Solusi
- Setting /var/www/parikesit.abimanyu.B25/.htaccess
  ```
  RewriteCond %{REQUEST_URI} /public/images
  RewriteCond %{REQUEST_URI} abimanyu
  RewriteRule ^(.*)$ public/images/abimanyu.png [L,R=301]
  ```
- Testing
  ```
  lynx parikesit.abimanyu.B25.com/public/images/halo-abimanyu.png
  ```






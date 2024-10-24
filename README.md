# readme-mod-3

[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-22041afd0340ce965d47ae6ef1cefeee28c7c493a6346c4f15d667ab976d596c.svg)](https://classroom.github.com/a/1zoHyFGp)
| Name           | NRP        | Kelas     |
| ---            | ---        | ----------|
| Felda Ega | 5025231199 | Jaringan Komputer D |
| Muhammad Rizal Hafiyyan | 5025231212 | Jaringan Komputer D |

## Put your topology config image here!

![Screenshot 2024-10-21 215027](https://github.com/user-attachments/assets/042c876e-3053-40ce-a988-8cc6637cb1e4)

![image](https://github.com/user-attachments/assets/a2b11533-d063-426f-b60c-2b6bbf252251)




<br>

> Template testing report: https://docs.google.com/document/d/17T0fsnh_4zZTrG-lELDJ88intrc9mkwCzZ_s-23JLCc/edit?usp=sharing

## Put your testing report here! 
> The report is sent in PDF format, uploaded to Drive, and set to public view.

https://docs.google.com/document/d/1KqxVpRxLr0ZUAPkTuEnJ-mqx8fNotaaF2fu41d5zRIE/edit?tab=t.0

## Soal 0

> Pada perlombaan akhir tahun kali ini, semua worker dan client ikut serta di dalamnya sebagai perwakilan dari masing-masing asrama. Persiapan yang dilakukan untuk perlombaan ini adalah dengan setup semua network configuration yang sesuai dengan tabel peran diatas. Khusus untuk client menggunakan konfigurasi dari DHCP Server.

> _For the end-of-year competition, all the workers and clients participate, representing their respective houses. The preparation includes setting up the network configuration as per the table above, with clients using DHCP Server configuration_

**Answer**

- Dumbledore:

```
auto eth0
iface eth0 inet dhcp

auto eth1
iface eth1 inet static
	address 10.127.1.1
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 10.127.2.1
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 10.127.3.1
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 10.127.4.1
	netmask 255.255.255.0

auto eth5
iface eth5 inet static
	address 10.127.5.1
	netmask 255.255.255.0

auto eth6
iface eth6 inet static
	address 10.127.6.1
	netmask 255.255.255.0

up iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 10.127.0.0/16
```

- SeverusSnape:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.3.2
	netmask 255.255.255.0
	gateway 10.127.3.1
  ```

- McGonagall:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.3.3
	netmask 255.255.255.0
	gateway 10.127.3.1
  ```

- Hagrid:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.4.2
	netmask 255.255.255.0
	gateway 10.127.4.1
  ```

- Voldemort:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.4.3
	netmask 255.255.255.0
	gateway 10.127.4.1
  ```

- Dementor:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.4.4
	netmask 255.255.255.0
	gateway 10.127.4.1
  ```

- HarryPotter:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.1.2
	netmask 255.255.255.0
	gateway 10.127.1.1
  ```

- RonWeasley:

  ```
  auto eth0
  iface eth0 inet static
	address 10.127.1.3
	netmask 255.255.255.0
	gateway 10.127.1.1
  ```

- HermioneGranger:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

- LunaLovegood:

  ```
    auto eth0
    iface eth0 inet static
	address 10.127.6.4
	netmask 255.255.255.0
	gateway 10.127.6.1
  ```

- FiliusFlitwick:

  ```
    auto eth0
    iface eth0 inet static
	address 10.127.6.3
	netmask 255.255.255.0
	gateway 10.127.6.1
  ```

- ChoChang:

  ```
    auto eth0
    iface eth0 inet dhcp
  ```

- DracoMalfoy:

  ```
  auto eth0
  iface eth0 inet dhcp  

  ```

- AstoriaGreengrass:

  ```
  auto eth0
  iface eth0 inet dhcp

  ```

- SusanBones:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

- HannahAbbott:

  ```
  auto eth0
  iface eth0 inet dhcp
  ```

## Soal 1

> Melakukan registrasi subdomain untuk PHP worker bernama gryffindor.hogwarts.yyy.com yang mengarah ke alamat IP load balancer Voldemort dan untuk laravel worker bernama ravenclaw.hogwarts.yyy.com yang mengarah ke alamat IP load balancer Dementor. Seluruh domain ini berkumpul dalam suatu ruang atau folder bernama hogwarts

> _Registering subdomains for the PHP workers named gryffindor.hogwarts.yyy.com, pointing to the IP Voldemort load balancer, and for the Laravel workers named ravenclaw.hogwarts.yyy.com, pointing to the IP Dementor load balancer. All domains are gathered in a folder named "hogwarts."_

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/fe3261d8-a930-4cb9-b984-b26ebb0e4671)

  ![image](https://github.com/user-attachments/assets/de8f33f6-d41f-4d47-b037-253fee1f5387)


- Configuration

  ```
  
  ```

- Explanation

```
  echo 'nameserver 192.168.122.1' > /etc/resolv.conf
  apt-get update
  apt-get install bind9 -y  

  nano /etc/bind/named.conf.local

  zone "gryffindor.hogwarts.d25.com" {
        type master;
        file "/etc/bind/hogwarts/gryffindor.hogwarts.d25.com";
};

zone "ravenclaw.hogwarts.d25.com" {
        type master;
        file "/etc/bind/hogwarts/ravenclaw.hogwarts.d25.com";
};

mkdir /etc/bind/hogwarts

nano /etc/bind/gogwarts/gryffindor.hogwarts.d25.com
;
;BIND data file for local loopback interface
;
$TTL    604800
@    IN    SOA    gryffindor.hogwarts.d25.com. root.gryffindor.hogwarts.d25.com. (
                2            ; Serial
                604800       ; Refresh
                86400        ; Retry
                2419200      ; Expire
                604800 )     ; Negative Cache TTL
;
@    IN    NS    gryffindor.hogwarts.d25.com.
@    IN    A     10.127.4.3

nano /etc/bind/gogwarts/ravenclaw.hogwarts.d25.com
;
;BIND data file for local loopback interface
;
$TTL    604800
@    IN    SOA    ravenclaw.hogwarts.d25.com. root.ravenclaw.hogwarts.d25.com. (
                2           ; Serial
                604800      ; Refresh
                86400       ; Retry
                2419200     ; Expire
                604800 )    ; Negative Cache TTL
;
@    IN    NS    ravenclaw.hogwarts.d25.com.
@    IN    A     10.127.4.4

service named restart
  ```

<br>

## Soal 2

> Memberikan ketentuan khusus untuk DracoMalfoy dan AstoriaGreengrass yang mendapat range IP dari [Prefix IP].2.64 - [Prefix IP].2.65 dan [Prefix IP].2.100 - [Prefix IP].2.101

> Selain itu, untuk HannahAbbott dan SusanBones mendapat range IP dari [Prefix IP].5.50 - [Prefix IP].5.51 dan [Prefix IP].5.155 - [Prefix IP].5.156.


> _Special provisions are given to DracoMalfoy and AstoriaGreengrass, who are assigned the IP range from [Prefix IP].2.64 - [Prefix IP].2.65 and [Prefix IP].2.100 - [Prefix IP].2.101._

> _Additionally, HannahAbbott and SusanBones are assigned the IP range from [Prefix IP].5.50 - [Prefix IP].5.51 and [Prefix IP].5.155 - [Prefix IP].5.156._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/3ccc12a3-c3d8-44de-ae33-fb9c53ca505e)

  ![image](https://github.com/user-attachments/assets/d6193fbd-416a-4eab-88f3-c6b3ed698aaa)

  ![image](https://github.com/user-attachments/assets/c94abf20-b2a7-4c73-8d41-a840a336bfb4)

  ![image](https://github.com/user-attachments/assets/8a9f3803-3d93-4105-8af8-051d7cf146d4)



- Configuration
```
  - DracoMalfoy:

  auto eth0
  iface eth0 inet dhcp  


- AstoriaGreengrass:

  auto eth0
  iface eth0 inet dhcp

- SusanBones:

  auto eth0
  iface eth0 inet dhcp

- HannahAbbott:

  auto eth0
  iface eth0 inet dhcp
```

- Explanation

```
Langkah" :

1. Periksa IP masing" client dengan ip a

2. Buka /etc/network/interfaces untuk Mengonfigurasi Interface Client, Edit file /etc/network/interfaces.

3. Hapus Konfigurasi yang Lama (Konfigurasi IP Address Statis), Lalu tambahkan konfigurasi berikut :
auto eth0
iface eth0 inet dhcp

4. Restart Masing" Client
menuju GNS3 → klik kanan Masing" Client → klik Stop → klik kanan kembali Client → klik Start.

5. Testing
Cek kembali IP Address masing" client dengan menjalankan ip a.

NB : Dilakukan pada masing" node client

```

<br>

## Soal 3

> Khusus untuk HermioneGranger yang berada di switch 1 mendapat range IP dari
[Prefix IP].1.10 - [Prefix IP].1.15 dan [Prefix IP].1.20 - [Prefix IP].1.25

> Khusus untuk ChoChang yang berada di switch 6 mendapat range IP dari 
[Prefix IP].6.10 - [Prefix IP].6.15 dan [Prefix IP].6.20 - [Prefix IP].6.25


> _HermioneGranger, who is on switch 1, is assigned the IP range from [Prefix IP].1.10 - [Prefix IP].1.15 and [Prefix IP].1.20 - [Prefix IP].1.25._

> _ChoChang, who is on switch 6, is assigned the IP range from [Prefix IP].6.10 - [Prefix IP].6.15 and [Prefix IP].6.20 - [Prefix IP].6.25._

**Answer:**

- Screenshot

  ![Screenshot 2024-10-23 000453](https://github.com/user-attachments/assets/594475b6-d4be-4ea7-84e7-1816fd42625f)

  ![image](https://github.com/user-attachments/assets/564eeb9a-d35d-4e31-9cb2-1f46772fcbcc)


- Configuration

  `Put your configuration in here`

- Explanation

```
subnet 10.127.1.0 netmask 255.255.255.0 {
    range 10.127.1.10 10.127.1.15;
    range 10.127.1.20 10.127.1.25;
    option routers 10.127.1.1;
    option broadcast-address 10.127.1.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 300;
    max-lease-time 6900;
}

subnet 10.127.6.0 netmask 255.255.255.0 {
    range 10.127.6.10 10.127.6.15;
    range 10.127.6.20 10.127.6.25;
    option routers 10.127.6.1;
    option broadcast-address 10.127.6.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 300;
    max-lease-time 6900;
}


```
<br>

## Soal 4

> Menetapkan batasan waktu untuk DHCP server dalam peminjaman alamat IP untuk client melalui switch 2 selama 5 menit sedangkan client yang melalui switch 5 selama 20 menit. Untuk switch 1 dan switch 6 memiliki batas waktu 10 menit. Alokasi waktu maksimal peminjaman alamat IP selama 100 menit. 

> _The DHCP server's lease time for IP addresses is set as follows: Clients connected through switch 2 have a lease time of 5 minutes, Clients connected through switch 5 have a lease time of 20 minutes, Switches 1 and 6 have a lease time of 10 minutes, The maximum lease time for IP addresses is set at 100 minutes._

**Answer:**

- Screenshot

  Switch 2

  ![Screenshot 2024-10-23 002802](https://github.com/user-attachments/assets/0a4a0a68-fb5b-43a2-9d11-aab83a7437a7)

  Switch 5

  ![Screenshot 2024-10-23 002930](https://github.com/user-attachments/assets/bc1eaf93-4a25-4802-b307-bf00c9aec097)

  Switch 1

  ![Screenshot 2024-10-23 002659](https://github.com/user-attachments/assets/7cf6150a-ecfb-428a-a47b-dc2606ebccb3)

  Switch 6

  ![Screenshot 2024-10-23 003016](https://github.com/user-attachments/assets/44f9492e-b822-4393-8903-c23ae4ce466f)


- Configuration

  `Put your configuration in here`

- Explanation

```
subnet 10.127.1.0 netmask 255.255.255.0 {
    range 10.127.1.10 10.127.1.15;
    range 10.127.1.20 10.127.1.25;
    option routers 10.127.1.1;
    option broadcast-address 10.127.1.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 600000;
    max-lease-time 6000000;
}

subnet 10.127.2.0 netmask 255.255.255.0 {
    range 10.127.2.64 10.127.2.65;
    range 10.127.2.100 10.127.2.101;
    option routers 10.127.2.1;
    option broadcast-address 10.127.2.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 300000;
    max-lease-time 6000000;
}

subnet 10.127.3.0 netmask 255.255.255.0 {
}

subnet 10.127.4.0 netmask 255.255.255.0 {
}

subnet 10.127.5.0 netmask 255.255.255.0 {
    range 10.127.5.50 10.127.5.51;
    range 10.127.5.155 10.127.5.156;
    option routers 10.127.5.1;
    option broadcast-address 10.127.5.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 1200000;
    max-lease-time 6000000;
}

subnet 10.127.6.0 netmask 255.255.255.0 {
    range 10.127.6.10 10.127.6.15;
    range 10.127.6.20 10.127.6.25;
    option routers 10.127.6.1;
    option broadcast-address 10.127.6.255;
    option domain-name-servers 10.127.3.2;
    default-lease-time 600000;
    max-lease-time 6000000;
}
```

<br>

## Soal 5

> Memastikan bahwa semua CLIENT, HermioneGranger, dan ChoChang harus menggunakan konfigurasi dari DHCP server, menerima DNS dari Professor McGonagall dan dapat akses internet. Khusus untuk HermioneGranger dan ChoChang mendapatkan IP Statis dari DHCP dengan [Prefix IP].x.14. hint: fixed address


> _Ensure that all CLIENT, HermioneGranger, and ChoChang use DHCP server configurations, receive DNS from Professor McGonagall, and can access the internet. HermioneGranger and ChoChang must receive static IPs from DHCP with the address [Prefix IP].x.14 (hint: fixed address)._

**Answer:**

- Screenshot

  ![image](https://github.com/user-attachments/assets/90073436-7b10-4f59-868a-2c8feea5d918)

  ![Screenshot 2024-10-23 145923](https://github.com/user-attachments/assets/86e9a183-ac46-4cf8-a721-b3c0e87f6b1d)

  ![Screenshot 2024-10-23 145824](https://github.com/user-attachments/assets/d5aa4205-1af2-4639-8530-ab4fd171d5d1)

  ![Screenshot 2024-10-23 145856](https://github.com/user-attachments/assets/5bc098f1-f435-4f04-a8fa-4b52cd9bfd7c)

  Hermione Granger

  ![Screenshot 2024-10-23 150115](https://github.com/user-attachments/assets/d113a964-e294-421a-843d-d233307894a0)

  ChoChang

  ![Screenshot 2024-10-23 150142](https://github.com/user-attachments/assets/2fd3b2f3-2e55-4202-8a27-79368765164c)

- Configuration

  `Put your configuration in here`

- Explanation
  nano /etc/dhcp/dhcpd.conf
```
subnet 10.127.1.0 netmask 255.255.255.0 {
    range 10.127.1.10 10.127.1.15;
    range 10.127.1.20 10.127.1.25;
    option routers 10.127.1.1;
    option broadcast-address 10.127.1.255;
    option domain-name-servers 10.127.3.3;
    default-lease-time 600000;
    max-lease-time 6000000;
}

subnet 10.127.2.0 netmask 255.255.255.0 {
    range 10.127.2.64 10.127.2.65;
    range 10.127.2.100 10.127.2.101;
    option routers 10.127.2.1;
    option broadcast-address 10.127.2.255;
    option domain-name-servers 10.127.3.3;
    default-lease-time 300000;
    max-lease-time 6000000;
}

subnet 10.127.3.0 netmask 255.255.255.0 {
}

subnet 10.127.4.0 netmask 255.255.255.0 {
}

subnet 10.127.5.0 netmask 255.255.255.0 {
    range 10.127.5.50 10.127.5.51;
    range 10.127.5.155 10.127.5.156;
    option routers 10.127.5.1;
    option broadcast-address 10.127.5.255;
    option domain-name-servers 10.127.3.3;
    default-lease-time 1200000;
    max-lease-time 6000000;
}

subnet 10.127.6.0 netmask 255.255.255.0 {
    range 10.127.6.10 10.127.6.15;
    range 10.127.6.20 10.127.6.25;
    option routers 10.127.6.1;
    option broadcast-address 10.127.6.255;
    option domain-name-servers 10.127.3.3;
    default-lease-time 600000;
    max-lease-time 6000000;
}

host HermioneGranger {
    hardware ethernet 52:bf:cd:0c:3c:84;
    fixed-address 10.127.1.14;
}

host ChoChang {
    hardware ethernet 06:a2:95:57:cb:7a;
    fixed-address 10.127.6.14;
}
```
<br>

## Soal 6

> Dimulai dari asrama Gryffindor yang menjadi PHP worker, mereka harus melakukan deployment untuk website berikut menggunakan PHP 7.4.

> _The Gryffindor house, represented by the PHP workers, must deploy the following website using PHP 7.4._

**Answer:**

- Screenshot

  HarryPotter

![image](https://github.com/user-attachments/assets/4b1f5e47-a7d8-43be-b028-cc53156b585e)


  RonWeasley

  ![image](https://github.com/user-attachments/assets/589cfb9a-44ba-49fa-ba08-97dcc89e1c8b)

  HermioneGranger

  ![Screenshot 2024-10-24 010546](https://github.com/user-attachments/assets/33668610-84c4-4cd0-a180-b8eba79ac891)

- Configuration

  `Put your configuration in here`

- Explanation
```
apt-get update
apt-get install nginx -y
apt-get install php php-fpm -y
apt-get install wget -y
apt-get install unzip -y
apt-get install lynx

mkdir /var/www/gryffindor.hogwarts.d25.com

wget -O /var/www/gryffindor.hogwarts.d25.com/gryffindor.hogwarts.d25.com "https://drive.google.com/uc?export=download&id=17R4Zcxm3emHq21WdMJzSfCxO8FHqvATM"

unzip -d /var/www/gryffindor.hogwarts.d25.com /var/www/gryffindor.hogwarts.d25.com/gryffindor.hogwarts.d25.com && rm /var/www/gryffindor.hogwarts.d25.com/gryffindor.hogwarts.d25.com

echo '
 server {

 	listen 80; 

 	root /var/www/gryffindor.hogwarts.d25.com;

 	index index.php index.html index.htm;
 	server_name gryffindor.hogwarts.d25.com;

 	location / {
 			try_files $uri $uri/ /index.php?$query_string;
 	}

 	# pass PHP scripts to FastCGI server
 	location ~ \.php$ {
 	include snippets/fastcgi-php.conf;
 	fastcgi_pass unix:/var/run/php/php7.4-fpm.sock;
 	}

 location ~ /\.ht {
 			deny all;
 	}

 	error_log /var/log/nginx/gryffindor.hogwarts.d25.com_error.log;
 	access_log /var/log/nginx/gryffindor.hogwarts.d25.com_access.log;
 }
' > /etc/nginx/sites-available/gryffindor.hogwarts.d25.com   

ln -s /etc/nginx/sites-available/gryffindor.hogwarts.d25.com /etc/nginx/sites-enabled

rm -rf /etc/nginx/sites-enabled/default

service nginx restart

service php7.4-fpm start

Testing

lynx http://10.127.1.3

```
<br>

## Soal 7

> Khusus perlombaan ini, Voldemort sudah jinak dan dia menjadi load balancer untuk para penghuni asrama Gryffindor yang menjadi worker PHP. Aturlah agar Voldemort dapat membagi pekerjaan kepada worker PHP secara optimal. Sebagai pengetesan awal, terapkan algoritma round robin dan lakukan test index.php menggunakan apache benchmark dengan 1000 request dan 100 request/second. Lakukan test sebanyak 3 kali lalu hitung rata-rata dan standar deviasi dari time/request

> _Voldemort, who is now reformed, becomes the load balancer for the Gryffindor PHP workers. Optimize Voldemort to distribute tasks to the PHP workers. For the initial test, apply the round-robin algorithm and test it to the index.php page using Apache Benchmark with 1,000 requests and 100 requests/second. Do the test 3 times and calculate the mean and standard deviation of time/request._

**Answer:**

- Screenshot

  ![Screenshot 2024-10-24 005344](https://github.com/user-attachments/assets/bb0ea463-b93a-4969-b946-1f3d50a5da48)
  
  ![Screenshot 2024-10-24 004836](https://github.com/user-attachments/assets/bbf47307-dce8-4641-a252-89872a6beb74)
  
  ![Screenshot 2024-10-24 004915](https://github.com/user-attachments/assets/7916f38d-4e96-4dc7-9c6a-f396d20fb5e0)
  
  ![Screenshot 2024-10-24 004938](https://github.com/user-attachments/assets/d5b74e32-02cb-4272-9947-b358f9a31bbc)





- Configuration

  `Put your configuration in here`

- Explanation

Load Balancer (Voldemort)

```
apt-get update
apt-get install nginx

echo '
upstream backend  {
 	server 10.127.1.2; #IP HarryPotter
 	server 10.127.1.3; #IP RonWeasley
	server 10.127.1.14; #IP HermioneGranger
}

server {
 	listen 80;
 	server_name gryffindor.hogwarts.d25.com;

 	location / {
	    proxy_pass http://backend;
            proxy_set_header    X-Real-IP $remote_addr;
            proxy_set_header    X-Forwarded-For $proxy_add_x_forwarded_for;
            proxy_set_header    Host $http_host;

            auth_basic "Administrator'/'''s Area";
            auth_basic_user_file /etc/nginx/.htpasswd;
 	}
	location ~ /\.ht {
            deny all;
        }

	error_log /var/log/nginx/lb_error.log;
	access_log /var/log/nginx/lb_access.log;
}
' > /etc/nginx/sites-available/lb-jarkom

ln -s /etc/nginx/sites-available/lb-jarkom /etc/nginx/sites-enabled

rm -rf /etc/nginx/sites-enabled/default

service nginx restart
```

Pada Client

```
apt-get update
apt-get install apache2 -y
apt-get install htop
ab -n 1000 -c 100 http://gryffindor.hogwarts.d25.com/
htop
apt-get install openjdk-11-jre
wget https://dlcdn.apache.org//jmeter/binaries/apache-jmeter-5.6.3.zip && unzip apache-jmeter-5.6.3.zip

```
 
<br>

## Soal 8

> Dalam penilaian akhir tahun ini, dibutuhkan algoritma terbaik, cobalah tes 3 algoritma load balancer dengan menggunakan jmeter. Jmeter perlu melakukan login, akses home, dan terakhir logout. Lakukan test dengan 300 thread dan 3 sec ramp up period. Lakukan test sebanyak 3 kali per algoritma, lalu hitung rata-rata dan standar deviasi dari response time. (username: wingardium, password: leviosa)


> _For the final assessment, try three different load-balancing algorithms using JMeter with 300 threads and a 3-second ramp-up period. Jmeter have to be able to login, access homepage, and logout. Do the test 3 times for each algorithm, then calculate the mean and standard deviation of response time. (username: wingardium, password: leviosa)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 9

> Tidak semua IP dapat akses asrama Gryffindor melalui IP Load balancer Voldemort. Untuk itu, berikan akses pada load balancer Voldemort. Autentikasi akan memerlukan username: “jarkom” dan password: “modul3”. Simpan file autentikasi pada  /etc/nginx/secretchamber 

> _Not all IPs can access Gryffindor's house through Voldemort’s load balancer. Grant access to the Voldemort load balancer. Authentication will require username: “jarkom” and password: “modul3”. Save the authentication file in /etc/nginx/secretchamber._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 10

> Setelah menambahkan autentikasi ke Gryffindor, coba testing ulang dengan menggunakan JMeter (algoritma round robin) serta skenario, thread, dan ramp up period yang sama seperti no 8 (300 thread, 3 sec ramp up period, login-home-logout). Kali ini, coba juga jumlah worker yang berbeda: 3 worker, 2 worker, dan 1 worker. 

> _After adding authentication to Gryffindor, retest using JMeter (round-robin algorithm) with the same scenario, thread, and ramp up period as number 8 (300 thread, 3 sec ramp up period, login-home-logout). This time, test with different numbers of workers: 3 workers, 2 workers, and 1 worker._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 11

> Hogwarts juga bekerjasama dengan ITS dalam perlombaan ini. Untuk itu, setiap request pada Voldemort yang mengandung /informatika pada akhir url akan di proxy passing menuju halaman https://www.its.ac.id/informatika/id/beranda/ 

> _Hogwarts has also partnered with ITS for this competition. Any request to Voldemort containing /informatika at the end of the URL should be proxied to the page at https://www.its.ac.id/informatika/id/beranda/._


**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 12

> Selain butuh autentikasi dalam pengaksesan asrama Gryffindor melalui LB Voldemort, juga perlu dibatasi dengan pembatasan IP.  LB Voldemort hanya boleh diakses oleh client dengan IP [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, dan [Prefix IP].5.155. hint: (fixed in dulu clientnya) 


> _In addition to requiring authentication for access to Gryffindor through Voldemort’s load balancer, IP restrictions also need to be enforced. Voldemort's load balancer can only be accessed by clients with IPs: [Prefix IP].2.64, [Prefix IP].2.100, [Prefix IP].5.50, and [Prefix IP].5.155. (hint: fixed client IPs first)._

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 13

> Pengaturan database yang dibutuhkan dalam perlombaan ini wajib diatur di Hagrid. Pastikan pengaturan database tersebut dapat diakses oleh Lunalovegood, FiliusFlitwick, dan ChoChang dengan menggunakan username: kelompokyyy dan password: passwordyyy 

> _Database setup for this competition is managed by Hagrid. Ensure that this database can be accessed by LunaLovegood, FiliusFlitwick, and ChoChang using the username: "kelompokyyy" and password: "passwordyyy”_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 14

> Selain itu, untuk Lunalovegood, FiliusFlitwick, dan ChoChang memiliki website sesuai dengan https://github.com/lodaogos/laravel-jarkom-modul-3/tree/main  berikut. Jangan lupa melakukan instalasi PHP8.0 dan Composer! Pastikan database di Hagrid sudah ada isinya sekarang dan server Laravel sudah running di localhost!

> _Additionally, LunaLovegood, FiliusFlitwick, and ChoChang have websites following this GitHub link: Laravel Jarkom Modul 3. Install PHP 8.0 and Composer! Make sure Hagrid's data storage is populated, and the Laravel servers are running on localhost!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 15

> Lakukan testing endpoint /register sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Kenapa failed 99x? Jelaskan! 

> _Test the /register endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Why did 99 tests fail? Explain!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 16

> Lakukan juga testing pada endpoint /login sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Dapatkan token melalui responsenya juga!

> _Test the /login endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Collect the token from the response!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 17

> Coba testing pada endpont /me sebanyak 100 request dengan 10 request/second di salah satu worker menggunakan apache benchmark dari SusanBones! Periksa responsenya apakah sudah sesuai dengan yang diloginkan? 

> _Test the /me endpoint with 100 requests and 10 requests per second on one of the workers using Apache Benchmark from SusanBones! Check if the response matches the logged-in user!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 18

> Mendekati tugas akhir perlombaan ini, mari seimbangkan kekuatan LunaLovegood, FiliusFlitwick, dan ChoChang untuk bekerja sama secara adil! Buatkan load balancer Laravel dengan Dementor dan implementasikan Proxy Bind untuk mengaitkan IP dari ketiga worker tersebut!

> _As the competition nears its end, balance the workload of LunaLovegood, FiliusFlitwick, and ChoChang! Create a Laravel load balancer using Dementor and implement Proxy Bind to link the IPs of the three workers!_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 19

> Untuk menguatkan para Laravel Worker, coba implementasikan PHP-FPM pada LunaLovegood, FiliusFlitwick, dan ChoChang. Untuk testing kinerja naikkan: 
pm.max_children
pm.start_servers
pm.min_spare_servers
pm.max_spare_servers
sebanyak tiga percobaan dan lakukan analisis testing menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _To strengthen the Laravel workers, implement PHP-FPM on LunaLovegood, FiliusFlitwick, and ChoChang. For performance testing, adjust: pm.max_children, pm.start_servers, pm.min_spare_servers, pm.max_spare_servers. Run the tests three times and analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>

## Soal 20

> Yey terakhir. Menurut Professor Dumbledore, sepertinya menggunakan PHP-FPM tidak cukup untuk meningkatkan performa worker-worker. Implementasikan Least-Conn pada Dementor. Lakukan analisis pada testing kinerja menggunakan apache benchmark sebanyak 100 request dengan 10 request/second atau menggunakan jmeter dengan 100 threads! (Pilih 1 metode testing)

> _Finally, Professor Dumbledore suggests that PHP-FPM might not be enough to improve the workers' performance. Implement the Least-Conn algorithm on Dementor. Analyze the performance by using Apache Benchmark with 100 requests at a rate of 10 requests per second or using JMeter with 100 threads! (Choose 1 testing method)_

**Answer:**

- Screenshot

  `Put your screenshot in here`

- Configuration

  `Put your configuration in here`

- Explanation

  `Put your explanation in here`

<br>
  
## Problems

## Revisions (if any)

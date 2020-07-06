# deploy apps on local with docker & docker-compose

#tested on linux and mac

#container & images 
* MYSQL
* PHPMYADMIN
* PHPFM
* NGINX

#Requirement
* Docker
* Docker Compose

#Instalasi di linux / mac
* Silakan clone repo ini 
* Silakan install docker di sistem anda, saya berasumsi docker sudah terinstall
* silakan install docker compose di sistem anda, saya berasumsi ini sudah terinstall
```bash
## masuk ke folder docker
cd /folder-docker
```
```bash
## build up images and contaner running
sudo docker-compose up -d --build, 
```
* tunggu proses ini sampai selesai, akan memakan waktu +- minutes
* done
```bash
###untuk mengecek apakah sudah berjalan 
docker container ls
```


#cara deploy app (contoh:laravel)
* note: silakan install composer
* buka docker-compose.yml
* tambahakn lokasi folder sistem di volume phpfm dan ngix, lihat gambar 1 dan gambar 2
![alt text](https://res.cloudinary.com/dk0053zbe/image/upload/v1592650544/Docker/phpfm_gpqlup.png)
gbr 1
![alt text](https://res.cloudinary.com/dk0053zbe/image/upload/v1592650544/Docker/nginx_tfgpsz.png)
gbr 2
![alt text](https://res.cloudinary.com/dk0053zbe/image/upload/v1592650544/Docker/vhost_i2lnnc.png)
gbr 3
* setting vhost lihat pada gambar 3
* registerkan port di nginx, contoh pada vhost kita buat projek kita-anak-indonesia di listen port 80, di nginx kita akan melakukan port forwading : jika user mengakses port 8080 kita akan forward ke port 80, contoh: (8080:80), di gambar 2 bisa anda lihat pada ports

* contoh diatas saya pakai kita-anak-indonesia (laravel  projek)
* pada .env laravel username database= root, password database = temp123
* jika sudah selesai, anda bisa menjalankan ulang service containernya

#Start container dengan docker-compose
```bash
sudo docker-compose up -d
```
#Mematikan service container
```bash
sudo docker-compose down
```
# Day 2

__Definisi Computer Network__
Menurut saya, computer network (jaringan komputer) adalah kumpulan dua atau lebih komputer yang saling terhubung melalui suatu media.

Contoh perintah linux yang digunakan untuk management server linux
- __Sudo__
atau super user do, berguna untuk melakukan suatu command sebagai user root tanpa harus login ke user root

- __Ls__
digunakan untuk menampilkan list atau daftar file

- __Mv__
digunakan untuk memindahkan atau rename suatu file

- __Cp__
digunakan untuk meng-copy file

- __Usermod__
digunakan untuk merubah informasi dari suatu user seperti group, nama, lokasi home directory, dll

- __Chmod__
digunakan untuk merubah permission atau ijin akses suatu file antara lain read, write, dan execute

- __Chown__
digunakan untuk merubah kepemilikan suatu file

### Merubah IP server Ubuntu dan Tes koneksi ip baru dengan SSH


1. Buka sudo nano /etc/netplan/00-installer-config.yaml dengan text editor nano

        sudo nano /etc/netplan/00-installer-config.yaml

![image](https://user-images.githubusercontent.com/40049149/186689489-336a4e14-fd56-4c5a-a756-2bc14ed4ed46.png)

2. Ubah parameter __ip__,__gateway__, dan __nameserver(dns)__ tersebut sesuai kebutuhan. __Save__ jika sudah __(ctrl + o)__, atau __exit__ dan __save__(__ctrl + x__, lalu __yes__)

![image](https://user-images.githubusercontent.com/40049149/186689702-54bc1aae-0c5d-4efe-89e1-fe0ea57e8d3c.png)

3. Lalu jalankan command berikut untuk meng-apply parameter yang kita masukkan sebelumnya

        sudo netplan apply
        
![image](https://user-images.githubusercontent.com/40049149/186690178-cbdeaef1-adb7-431a-812b-e072455bc0bc.png)
        
4. Connect ke ip baru yang dimasukkan sebelumnya (close terminal jika stuck)

![image](https://user-images.githubusercontent.com/40049149/186690531-467c908f-11e2-4fe2-8af5-c63972d7d3be.png)

5. Untuk mengecek ip saat ini, bisa menggunakan command berikut

        ip a

![image](https://user-images.githubusercontent.com/40049149/186690718-fefcb881-7090-4659-8b0c-a56943be874d.png)

6. Cek koneksi dengan ping atau traceroute

        ping google.com
        
![image](https://user-images.githubusercontent.com/40049149/186691032-8d4d9794-6939-4914-8a47-bb705c7131e7.png)


### Cara install LocalTunel


1. Pertama-tama yang kita lakukan adalah instalalsi node.js menggunakan nvm untuk melakukan instalasi kalian dapat mengikuti langkah-langkah dibawah ini.

        sudo apt install curl
        
![image](https://user-images.githubusercontent.com/40049149/186681818-eb9d1344-c0de-4e4d-ac0e-d04a0811e540.png)

        curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash

![image](https://user-images.githubusercontent.com/40049149/186214585-2ea61553-c88b-4a7a-8f44-7617b6b321a8.png)

        exec bash
        sudo apt install nodejs
        
![image](https://user-images.githubusercontent.com/40049149/186215429-51ef0a2a-098b-4c23-a344-e33ec78ba058.png)

        sudo apt install npm
        
![image](https://user-images.githubusercontent.com/40049149/186216762-1af42a0e-a0c6-43fd-ade1-eb9aa73b24b1.png)

        node -v
        npm -v

![image](https://user-images.githubusercontent.com/40049149/186217071-57527c3c-2507-4b09-8698-5a907c84c238.png)


2. Selanjutnya kita akan melakukan instalasi localtunnel menggunakan npm yang sudah kita install.

        sudo npm install -g localtunnel

![image](https://user-images.githubusercontent.com/40049149/186299160-c6da4d47-2cf1-4d4b-98f9-d95a6875aac3.png)
      
3. Sekarang kita akan melakukan instalasi __apache__ yang sama seperti pertemuan sebelumnya.

        sudo apt install apache2
        
Lalu nanti akan muncul notifikasi Do you want to continue? [Y/n] kalian ketik saja Y. Jika sudah maka instalasi akan berjalan.

![image](https://user-images.githubusercontent.com/40049149/186299483-44f9e4e4-8ec2-41f4-8d59-9d415d1536a8.png)

5. Jika instalasi kalian telah selesai melakukan instalasi __Apache__, Selanjutnya kita coba untuk mengakses __Apache__ di web browser kita untuk mengecek apakah __Apache__ kita sudah berjalan atau belum.

   Coba kalian akses di web browser kalian, lalu masukkan IP dari server kalian.

![image](https://user-images.githubusercontent.com/40049149/186299860-809ae2c1-1cf0-4a82-b0e4-52b58670ed3d.png)

6. Sekarang kita coba untuk menggunakan localtunel untuk aplikasi Nginx yang sudah kita install.

   Untuk menjalankan localtunel kalian dapat mengikuti perintah di bawah ini.

        lt --port 80

![image](https://user-images.githubusercontent.com/40049149/186300141-be518754-bc0f-4be8-92a5-3b8a5c6ffbdb.png)

   keterangan : pastikan dibagian port telah sesuai dengan aplikasi kalian. Karena setiap aplikasi pasti mempunyai port yang berbeda-beda, kita ambil contoh saja dari aplikasi node.js, aplikasi node.js biasanya berjalan di atas port 3000.

7. Jika sudah copy url yang ada di terminal kalian.

   Setelah itu coba kalian akses menggunakan Web.browser kalian.

![image](https://user-images.githubusercontent.com/40049149/186300306-0686d4d9-570b-44c8-872c-3b805dc19445.png)

8. Jika sudah klik tombol Click to Continue.

   Selanjutnya kalian akan di arahkan ke aplikasi kalian. Dan aplikasi kalian sekarang sudah dapat di akses oleh public.

![image](https://user-images.githubusercontent.com/40049149/186300456-d0590d78-bbfa-4ee7-a3c6-837cde8e13ca.png)

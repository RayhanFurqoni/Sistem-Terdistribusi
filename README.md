![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/887c41f5-449f-4dae-98c4-d899a1a954d5)![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/aa76a0ba-23d3-4a57-bea8-2ea475010982)# Sistem-Terdistribusi
**step pertama** download ubuntu 22.04.3 LTS di microsoft store
- memberi nama dan password
  
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/fb5aed25-f1f3-4ccb-a66f-a78d5eac7af5)

- command sudo apt install -y build-essential linux-headers-$(uname -r)
  
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/05bab0d7-0a71-4f21-98dc-cb9f27c750a6)

- karena ada error seperti dibawah, kita ubah sources list (sudo nano /etc/apt/sources.list)
**E: Unable to locate package linux-headers-4.4.0-19041-Microsoft
E: Couldn't find any package by glob 'linux-headers-4.4.0-19041-Microsoft'**
- setelah masuk ke source list kita mengganti menjadi
  
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/9f108373-4006-4d44-a4bc-d6b1d66cb9db)


-command apt upgrade -y ternyata error
**E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?**
- karena error kita update terlebih dahulu ubuntu nya dengan sudo apt upgrade -y
  
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/7ceebef2-9507-4990-80fe-d60c42229d10)

- selanjutnya instal lxc dengan sudo apt-get install lxc lxctl lxc-templates net-tools

  
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/a3ea00e1-9229-463b-9a75-ce0e66a92829)

- sudo lxc-checkconfig (pastikan semua enable)

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/8840af95-7f1a-40bd-b236-5f808665f7be)

- command sudo ls /usr/share/lxc/templates/ untuk melihat ada file apa saja

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/3cdde7f7-b3d7-4d76-ae5c-59572bd03f1a)

- install nginx dengan command "sudo apt install nginx nginx-extras"

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/e7721774-6d26-4776-96eb-b7b79109dba3)

- kemudian masuk ke folder cd /etc/nginx/sites-enabled

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/c5df1e34-6e0b-489a-92e8-bdadacd87bee)

- kemudian bikin file sister.local
- sudo cp default sister.local
- masuk ke isi file sister.local dengan "sudo nano sister.local" dan hapus semua isi kecuali
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/0a016167-d6ed-4e74-84a6-e41d3b80134c)
- cek apakah nginx sudah berhasil dengan command "sudo nginx -t"
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/23e40f6a-0ecc-4a4b-b82c-ac3f435821a4)

- reload nginx dengan "sudo nginx -s reload"
- masuk ke file cd /var/www/html/
- membuat salinan copy dengan " sudo cp index.nginx-debian.html index.html"

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/afc3ad1b-15a0-4b19-9e64-9668418f537b)

- merubah isi dari file index.html dengan "sudo nano index.html"

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/021529c2-9b24-4f62-a4c8-653fe2c1dfdb)

- Buka notepad administrator, dan cari file hosts di C:\Windows\System32\drivers\etc
- setelah membuka file hosts, tambahkan file baru

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/363873d0-3f00-4c9d-b13a-631a709ed6cb)

- buka browser dan ketikkan sister.local

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/6d32241e-b830-4cad-8678-30968b9c08a8)

- membuat LXC dengan nama ubuntu_php5.6 (dengan ubuntu 16.04) dan ubuntu_php7.4 (dengan ubuntu 18.04)
microservice 1 = sudo lxc-create -n microservice1 -t download -- --dist ubuntu --release focal --arch amd64 --force-cache --server images.linuxcontainers.org

microservice 2 = sudo lxc-create -n microservice2 -t download -- --dist ubuntu --release bionic --arch amd64 --force-cache --server images.linuxcontainers.org

-kemudian start microservicenya kita, kita mulai dari microservice2 dengan command " sudo lxc-start -n microservice2"
- sudo lxc-attach -n microservice2
- buat password untuk microservice2
- 
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/4eed202e-056f-4f0e-8a41-2f28beb56117)


- kemudian cek ip nya dengan command "ip a"

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/c6275e8d-2b6c-4eac-bf8d-5916c80df74f)

  - kemudian install nano "apt install nano"

   ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/e0b1d7c1-56c8-405c-94c9-09c812787589)

  -  rubah file 10-lxc.yaml dengan "sudo nano /etc/netplan/10-lxc.yaml"
  -  rubah ip file 10-lxc.yaml dan yang lainnya seperti gambar dibawah

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/fc3d39c4-ed11-4568-893e-838ceefba76b)

  -  kemudian refresh dengan "sudo netplan apply"

 ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/b05d4954-2517-4a91-ad76-0ae3c7ed351c)

  - **sekarang kita ke microservice 1, untuk langkah langkah sama dengan microservice2**
  - start microservice1 dengan "sudo lxc-start -n microservice1"
  - rubat ke root dengan "sudo lxc-attach -n microservice1"
  - install nano "apt install nano"
  - masuk kefile 10-lxc.yaml " sudo nano /etc/netplan/10-lxc.yaml"

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/1e799e53-2f37-47dc-b34b-430d6d600357)

  - 
- rubah file 10-lxc.yaml seperti dibawah

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/92920424-9d24-42a0-b040-dd525a909dcd)

- kemudian refresh dengan "sudo netplan apply"
- selanjutnya tes ping kegoogle.com
- dan terakhir update microservice1 dan microservice2 dengan "apt upgrade -y"

**MICROSERVICE ABOUTUS**
- install nginx dengan "sudo apt install nginx nginx-extras"
- setelah menginstall, masuk ke folder var/www/html dan disana ada file index.nginx-debian.html
- masuk ke file nya dan ganti isi about us sesuai yang diinginkan(microservice2)
-  kemudian apt install curl
-  cek apakah sudah terganti dengan "curl localhost"

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/459d4f7e-028e-44ce-b0fb-4361e9fda5db)

-- membuat file mcsv2.local dan merubah server name dan root

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/b944c00a-ec9d-4999-9a7f-db0317210d01)


- masuk ke folder /var/www/html kemudian copy index.html dengan " cp index.nginx-debian.html index html"
- kemudian masuk ke file hosts dengan "sudo nano /etc/hosts" dan menambahkan hosts baru yaitu **mscv2.local**

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/b98c48d1-c562-404e-80f9-7b91d69f3bda)


**MICROSERVICE BLOG**
- install nginx dengan "sudo apt install nginx nginx-extras"
- setelah menginstall, masuk ke folder var/www/html dan disana ada file index.nginx-debian.html
- masuk ke file nya dan ganti isi blog sesuai yang diinginkan(microservice1)
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/f56b1b45-f0b4-4c69-931a-d5fd0d0931b8)
- kemudian apt install curl
- cek apakah sudah terganti dengan "curl localhost"
  
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/4629ebe5-4ddf-4011-82bf-f149faf617c7)

-- membuat file mcsv1.local dan merubah server name dan root

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/ef3dc790-8010-40fb-9fa0-1ddde7d2de28)

- masuk ke folder /var/www/html kemudian copy index.html dengan " cp index.nginx-debian.html index html"
- kemudian masuk ke file hosts dengan "sudo nano /etc/hosts" dan menambahkan hosts baru yaitu **mscv1.local**

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/c43c81f7-1165-4b9c-8db5-c68fd6e98fec)

- 

- 

  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/c491dec0-fe14-4ad1-ad84-e0d90182e91f)

**kembali ke ubuntu utama**
- masuk ke folder /etc/nginx/sites-enabled/
- 
- masuk kefile dan membuat link untuk ke microservice1 jika ingin kemenu blog, dan jika ingin ke aboutus link ke microservice2
**Langkah 1**
  - menambahkan mcsv1.local dan mcsv2.local yang sudah kita buat di /etc/hosts
  
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/9860982f-ba40-4fc7-bb60-f5227c9f447b)

**Langkah 2**
- menambahkan link yang akan ditujukan di sister.local

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/3b9afca3-5f31-47a6-8e1b-2be502bd4f47)

**HASIL NYA**

- WEB SISTER.LOCAL

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/21b36f79-55f4-4bd0-8cda-0894ecdac121)


WEB SISTER.LOCAL/ABOUT US

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/21904d17-c96e-40bf-ab1a-c3c8270db4f9)

WEB SISTER.LOCAL/BLOG

![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/59875e2b-098d-4861-8c2f-88e247b9cf1f)



-  




  

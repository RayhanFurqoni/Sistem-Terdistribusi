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

- 




  

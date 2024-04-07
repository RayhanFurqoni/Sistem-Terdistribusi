# Sistem-Terdistribusi
**step pertama** download ubuntu 22.04.3 LTS di microsoft store
- memberi nama dan password
- command sudo apt install -y build-essential linux-headers-$(uname -r)
- karena ada error seperti dibawah kita ubah sources list (sudo nano /etc/apt/sources.list)
**E: Unable to locate package linux-headers-4.4.0-19041-Microsoft
E: Couldn't find any package by glob 'linux-headers-4.4.0-19041-Microsoft'**
- setelah masuk ke source list kita mengganti menjadi
**deb http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy main restricted universe multiverse**

**deb http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-updates main restricted universe multiverse**
**deb http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-security main restricted universe multiverse**

**deb http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse
deb-src http://archive.ubuntu.com/ubuntu/ jammy-backports main restricted universe multiverse**

**deb http://archive.canonical.com/ubuntu/ jammy partner**
**deb-src http://archive.canonical.com/ubuntu/ jammy partner**

-command apt upgrade -y ternyata error
**E: Could not open lock file /var/lib/dpkg/lock-frontend - open (13: Permission denied)
E: Unable to acquire the dpkg frontend lock (/var/lib/dpkg/lock-frontend), are you root?**
- karena error kita update terlebih dahulu ubuntu nya dengan sudo apt upgrade -y
- selanjutnya instal lxc dengan sudo apt-get install lxc lxctl lxc-templates net-tools
- sudo lxc-checkconfig (pastikan semua enable
- command sudo ls /usr/share/lxc/templates/ untuk melihat ada file apa saja
- install nginx dengan command "sudo apt install nginx nginx-extras"
- kemudian masuk ke folder cd /etc/nginx/sites-enabled
- kemudian bikin file sister.local
- sudo cp default sister.local
- masuk ke isi file sister.local dengan "sudo nano sister.local" dan hapus semua isi kecuali
  ![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/0a016167-d6ed-4e74-84a6-e41d3b80134c)
- cek apakah nginx sudah berhasil dengan command "sudo nginx -t"
![image](https://github.com/RayhanFurqoni/Sistem-Terdistribusi/assets/124054176/23e40f6a-0ecc-4a4b-b82c-ac3f435821a4)


  

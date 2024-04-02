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
- karena error kita update terlebih dahulu ubuntu nya dengan sudo apt apt upgrade -y
- selanjutnya instal lxc dengan sudo apt-get install lxc lxctl lxc-templates net-tools 

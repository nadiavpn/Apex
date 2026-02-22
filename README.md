## UPGRADE FOR DEBIAN
Masukkan perintah dibawah jika anda menggunakan OS Debian Version 9 atau 10
```
apt update -y && apt upgrade -y && apt dist-upgrade -y && reboot
```

##  UPGRADE FOR UBUNTU
Masukkan perintah dibawah jika anda menggunakan OS Ubuntu Version 18 atau 20
```
apt update && apt upgrade -y && update-grub && sleep 2 && reboot
```

## INSTALL SCRIPT 
Masukkan perintah dibawah untuk menginstall Autoscript Premium by nadiavpn
```
apt update -y && apt upgrade -y
apt install -y curl wget ca-certificates unzip gnupg lsb-release coreutils
wget -q https://raw.githubusercontent.com/nadiavpn/Apex/main/ubu20-deb10-stable.sh
chmod +x ubu20-deb10-stable.sh
./ubu20-deb10-stable.sh

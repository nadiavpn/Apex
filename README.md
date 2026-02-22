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

## `WAJIB IZIN IP, SILAHKAN HUBUNGI ADMIN !`
Nadia :
<br><br><a href="https://wa.me/+6285973781816" target=”_blank”><img src="https://img.shields.io/static/v1?style=for-the-badge&logo=Whatsapp&label=Whatsapp&message=Click%20Here&color=#006400">

## UPDATE SCRIPT
#!/usr/bin/env bash
set -Eeuo pipefail

export DEBIAN_FRONTEND=noninteractive
export PATH="/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin:/sbin:/bin"
umask 022

LOG_FILE="/var/log/apex-install.log"
mkdir -p "$(dirname "$LOG_FILE")"
exec > >(tee -a "$LOG_FILE") 2>&1

trap 'echo "[ERROR] Gagal di baris $LINENO. Cek log: $LOG_FILE" >&2' ERR

if [[ "${EUID:-$(id -u)}" -ne 0 ]]; then
  echo "[ERROR] Jalankan sebagai root (sudo -i)" >&2
  exit 1
fi

source /etc/os-release || true
case "${ID:-}" in
  ubuntu|debian) : ;;
  *) echo "[ERROR] OS tidak didukung: ${ID:-unknown} ${VERSION_ID:-unknown}" >&2; exit 1 ;;
esac

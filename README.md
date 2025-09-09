# 📦 MiniPC configuration basics

This project documents basic setup

---

## 📂 Disk automount - startup

```bash
Create a folder:
sudo mkdir -p /mnt/t9medialibrary

Edit the /etc/fstab following the syntax:

eugeneb@n100:/mnt/satamedialibrary$ cat /etc/fstab 
# /etc/fstab: static file system information.
#
# Use 'blkid' to print the universally unique identifier for a
# device; this may be used with UUID= as a more robust way to name devices
# that works even if disks are added and removed. See fstab(5).
#
# <file system> <mount point>   <type>  <options>       <dump>  <pass>
# / was on /dev/nvme0n1p1 during curtin installation
/dev/disk/by-uuid/609272d2-a84f-49cc-a260-cdd89be2ce2c / ext4 defaults 0 1
# /home was on /dev/nvme0n1p3 during curtin installation
/dev/disk/by-uuid/3257aa9d-edc3-4693-9657-4228a76b2a09 /home ext4 defaults 0 1
# /boot/efi was on /dev/nvme0n1p2 during curtin installation
/dev/disk/by-uuid/B5E3-E5F4 /boot/efi vfat defaults 0 1
/dev/sda1   /mnt/satamedialibrary   ext4   defaults   0   2
/dev/sdb1   /mnt/t9medialibrary   ext4   defaults   0   2
/swap.img	none	swap	sw	0	0
```

## 🔧 Install Disk Usage analyzer for Ubuntu

```bash
sudo apt install ncdu

ncdu usage:
ncdu
```

## ⚙️ CasaOS

[CasaOS Github page](https://github.com/IceWhaleTech/CasaOS)

```bash
wget -qO- https://get.casaos.io | sudo bash
```
or
```bash
curl -fsSL https://get.casaos.io | sudo bash
```

## ⚙️ Docker containers to install:

- 🎬 **Jellyfin** – Media server
- 📊 **Jellystat** – Jellyfin statistics & analytics
- 📥 **qBittorrent** – Torrent client
- 📈 **btop** – Resource monitor
- 📝 **Trilium** – Notes & knowledge base
- 📊 **Scrutiny** – Disk monitoring
- 🚀 **OpenSpeedTest** – Lan Network speed testing
- 🎞️ **mkvtoolnix** – MKV video tools


## 📂 Skin Directory Structure for qBittorent/Vuetorrent

My setup is located under:

```bash
Host: /mnt/home/eugeneb/AppData/qbittorrentSystemfiles/vuetorrent 
Container: /systemfiles

Write directory:
eugeneb@n100:~$ cd /mnt/home/eugeneb/AppData/qbittorrentSystemfiles/vuetorrent
eugeneb@n100:/mnt/home/eugeneb/AppData/qbittorrentSystemfiles/vuetorrent$ ls -la
total 36
drwxrwxrwx 3 root root 4096 Oct 27  2024 .
drwxrwxrwx 3 root root 4096 Oct 27  2024 ..
-rwxrw-rw- 1 root root 6148 Oct 27  2024 .DS_Store
-rwxrw-rw- 1 root root 4096 Mar  2  2025 ._.DS_Store
-rwxrw-rw- 1 root root 4096 Mar  2  2025 ._public
-rwxrw-rw- 1 root root 4096 Mar  2  2025 ._version.txt
drwxrwxrwx 4 root root 4096 Oct 21  2024 public
-rwxrw-rw- 1 root root    6 Oct 21  2024 version.txt
eugeneb@n100:/mnt/home/eugeneb/AppData/qbittorrentSystemfiles/vuetorrent$
```

---

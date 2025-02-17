# Pertemuan 2: Interface dan Perintah Dasar Kali Linux

## Apersepsi (15 menit)
Sistem operasi Kali Linux memiliki banyak tools untuk ethical hacking. Untuk menggunakannya dengan efektif, kita perlu memahami interface dan perintah dasar terminal Linux.

## Tujuan Pembelajaran
1. Memahami interface Kali Linux
2. Menguasai perintah dasar terminal
3. Mampu melakukan konfigurasi sistem dasar

## Materi

### 1. Pengenalan Interface Kali Linux (45 menit)
#### A. Desktop Environment
- XFCE/GNOME/KDE
- Panel dan menu
- System tray
- Workspace

#### B. Bantuan Interface
```bash
# Melihat versi desktop environment
echo $DESKTOP_SESSION
echo $XDG_CURRENT_DESKTOP

# Cek window manager
wmctrl -m
```

### 2. Perintah Dasar Terminal (45 menit)
#### A. Navigasi File System
```bash
# Perintah dasar direktori
pwd     # Lokasi saat ini
ls      # List files
cd      # Pindah direktori
mkdir   # Buat direktori

# File operations
cp      # Copy file
mv      # Move/rename file
rm      # Hapus file
touch   # Buat file kosong
```

#### B. File Management
```bash
# Melihat isi file
cat     # Tampilkan seluruh isi
head    # Tampilkan awal file
tail    # Tampilkan akhir file
less    # Scroll isi file

# File permissions
chmod   # Ubah permission
chown   # Ubah kepemilikan
```

### 3. Konfigurasi Sistem Dasar (90 menit)
#### A. Network Setup
```bash
# Cek network interface
ip addr
ifconfig

# Konfigurasi network
sudo nano /etc/network/interfaces
sudo systemctl restart networking
```

#### B. Package Management
```bash
# Update sistem
sudo apt update
sudo apt upgrade

# Install/remove package
sudo apt install package_name
sudo apt remove package_name
```

## Praktikum
### 1. Terminal Navigation
```bash
# Buat struktur direktori
mkdir -p ~/test/{dir1,dir2,dir3}
cd ~/test
touch file1 file2
ls -la
```

### 2. File Operations
```bash
# Copy dan move files
cp file1 dir1/
mv file2 dir2/
ln -s dir1/file1 link1
```

### 3. System Configuration
```bash
# Cek system info
uname -a
lsb_release -a
free -h
df -h
```

## Tugas
1. Buat cheat sheet perintah Linux
2. Konfigurasi network interface
3. Instalasi dan konfigurasi tools dasar

## Referensi
1. [Kali Linux Terminal Manual](https://www.kali.org/docs/general-use/)
2. [Linux Command Line Basics](https://linuxcommand.org/)
3. [XFCE Documentation](https://docs.xfce.org/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari konsep OSINT
2. Siapkan target untuk information gathering
3. Baca dokumentasi tools OSINT

*Note: Praktek perintah terminal secara rutin untuk membangun muscle memory.*
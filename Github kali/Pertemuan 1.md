# Pertemuan 1: Pengenalan Ethical Hacking dan Keamanan Siber

## Pendahuluan
### Deskripsi Singkat
Pertemuan ini membahas konsep dasar ethical hacking dan keamanan siber, termasuk prinsip-prinsip fundamental, metodologi, dan aspek legal serta etika dalam ethical hacking.

### Tujuan Pembelajaran
Setelah mengikuti pertemuan ini, peserta diharapkan dapat:
1. Memahami konsep dasar keamanan siber
2. Menjelaskan prinsip CIA Triad
3. Mengidentifikasi berbagai jenis ancaman keamanan
4. Memahami metodologi ethical hacking
5. Mengenal tools dasar dalam Kali Linux

### Waktu
Total: 6 jam (360 menit)
- Teori: 4 jam
- Praktikum: 2 jam

### Metode Pembelajaran
1. Ceramah interaktif
2. Demonstrasi
3. Praktikum
4. Diskusi kelompok

## Materi Pembelajaran

### 1. Pengenalan Ethical Hacking (45 menit)
#### A. Definisi dan Konsep
- Ethical Hacking vs Cyber Crime
- Peran Ethical Hacker
- Metodologi Ethical Hacking

#### B. Bantuan Pembelajaran
```bash
# Melihat versi Kali
cat /etc/os-release

# Cek tools ethical hacking
ls /usr/share/
```

### 2. Aspek Legal dan Etika (45 menit)
#### A. Regulasi dan Hukum
- UU ITE
- Izin pengujian
- Batasan legal

#### B. Kode Etik
- Responsible disclosure
- Dokumentasi pengujian
- Kerahasiaan data

### 3. Instalasi Kali Linux (90 menit)
#### A. Persiapan Instalasi
```bash
# Cek sistem
uname -a
lsb_release -a

# Cek disk
fdisk -l
df -h
```

#### B. Proses Instalasi
1. Download ISO Kali Linux
2. Buat bootable USB
3. Partisi disk
4. Instalasi sistem

#### C. Konfigurasi Awal
```bash
# Update sistem
sudo apt update
sudo apt upgrade

# Cek koneksi
ping -c 3 google.com
```

## Praktikum
### 1. Instalasi VirtualBox
```bash
# Install VirtualBox
sudo apt install virtualbox
```

### 2. Instalasi Kali Linux di VM
- Buat VM baru
- Alokasi resource
- Mount ISO
- Ikuti wizard instalasi

### 3. Konfigurasi Dasar
```bash
# Set keyboard
setxkbmap -layout us

# Set timezone
sudo dpkg-reconfigure tzdata
```

## Tugas
1. Instalasi Kali Linux (VM/Bare Metal)
2. Dokumentasi proses instalasi
3. Identifikasi tools yang tersedia

## Referensi
1. [Kali Linux Documentation](https://www.kali.org/docs/)
2. [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
3. [Ethical Hacking Laws](https://www.eccouncil.org/ethical-hacking/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari interface Kali Linux
2. Siapkan terminal emulator
3. Baca dokumentasi perintah dasar Linux

*Note: Pastikan selalu mengikuti aspek legal dan etika dalam setiap aktivitas ethical hacking.*
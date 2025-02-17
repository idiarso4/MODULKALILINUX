# Pertemuan 3: Information Gathering

## Apersepsi (15 menit)
Sebelum melakukan pengujian keamanan, kita perlu mengumpulkan informasi tentang target. Information gathering yang efektif akan membantu menemukan celah keamanan potensial.

## Tujuan Pembelajaran
1. Memahami konsep OSINT
2. Melakukan DNS enumeration
3. Melakukan network scanning
4. Menganalisis hasil information gathering

## Materi

### 1. OSINT (Open Source Intelligence) (45 menit)
#### A. Teknik OSINT
- Google dorks
- Social media intelligence
- Domain research
- Email harvesting

#### B. OSINT Tools
```bash
# TheHarvester
theHarvester -d target.com -b all

# Maltego
maltego &

# Recon-ng
recon-ng
help modules
```

### 2. DNS Enumeration (45 menit)
#### A. DNS Reconnaissance
```bash
# Basic DNS lookup
nslookup target.com
dig target.com

# Zone transfer
dig axfr @ns1.target.com target.com

# DNS tools
dnsenum target.com
dnsrecon -d target.com
```

#### B. Subdomain Discovery
```bash
# Subdomain enumeration
sublist3r -d target.com
amass enum -d target.com

# Brute force
gobuster dns -d target.com -w wordlist.txt
```

### 3. Network Scanning (90 menit)
#### A. Port Scanning
```bash
# Basic scan
nmap target.com

# Comprehensive scan
nmap -sS -sV -O -p- target.com

# Script scanning
nmap --script vuln target.com
```

#### B. Service Enumeration
```bash
# Banner grabbing
nc -v target.com 80
telnet target.com 25

# Service detection
nmap -sV --version-intensity 5 target.com
```

## Praktikum
### 1. OSINT Collection
```bash
# Create target list
echo "target.com" > targets.txt

# Run OSINT tools
theHarvester -d target.com -b google,linkedin
```

### 2. DNS Analysis
```bash
# DNS enumeration
dnsrecon -d target.com -t std
dnsenum --noreverse target.com
```

### 3. Network Discovery
```bash
# Network mapping
nmap -sn 192.168.1.0/24
netdiscover -r 192.168.1.0/24
```

## Tugas
1. OSINT report untuk target yang ditentukan
2. DNS mapping dan analisis
3. Network scanning report

## Referensi
1. [OSINT Framework](https://osintframework.com/)
2. [Nmap Documentation](https://nmap.org/book/man.html)
3. [DNS Security](https://www.dns.com/support/dns-security-best-practices/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari konsep vulnerability assessment
2. Siapkan tools scanning
3. Baca dokumentasi vulnerability scanner

*Note: Selalu lakukan information gathering dengan izin yang tepat dan dalam lingkungan yang terkontrol.*
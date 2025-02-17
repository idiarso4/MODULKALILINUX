# Pertemuan 4: Praktikum Information Gathering

## Apersepsi (15 menit)
Setelah mempelajari berbagai teknik information gathering, kita akan mempraktekkan secara langsung bagaimana mengumpulkan informasi tentang target secara etis dan sistematis.

## Tujuan Pembelajaran
1. Mempraktekkan teknik information gathering
2. Mendokumentasikan hasil pengumpulan informasi
3. Menganalisis temuan secara sistematis
4. Membuat laporan yang terstruktur

## Materi

### 1. Persiapan Praktikum (30 menit)
#### A. Setup Environment
```bash
# Cek koneksi internet
ping -c 3 google.com

# Update tools
sudo apt update
sudo apt install -y nmap whois dnsutils
```

#### B. Target Identification
```bash
# Membuat file target
echo "target.com" > targets.txt

# Basic DNS check
host target.com
```

### 2. OSINT Gathering (45 menit)
#### A. Domain Information
```bash
# WHOIS lookup
whois target.com > whois_results.txt

# DNS information
dig target.com ANY
host -a target.com
```

#### B. Email & Employee Info
```bash
# TheHarvester scan
theHarvester -d target.com -b google,linkedin -l 500

# Save results
theHarvester -d target.com -b all -f results.html
```

### 3. Network Enumeration (45 menit)
#### A. Network Discovery
```bash
# Basic network scan
nmap -sn 192.168.1.0/24

# Service detection
nmap -sV -F target.com

# OS detection
nmap -O target.com
```

#### B. Port Analysis
```bash
# Full port scan
nmap -p- target.com

# Version detection
nmap -sV --version-intensity 5 target.com
```

### 4. Web Reconnaissance (45 menit)
#### A. Web Technology
```bash
# Whatweb scan
whatweb -v target.com

# Wappalyzer CLI
wappalyzer target.com
```

#### B. Directory Enumeration
```bash
# Directory scanning
dirb http://target.com

# Gobuster scan
gobuster dir -u target.com -w /usr/share/wordlists/dirb/common.txt
```

### 5. Documentation (45 menit)
#### A. Data Organization
```bash
# Create report structure
mkdir -p ~/pentest/{recon,scan,web,report}

# Organize results
mv *_results.txt ~/pentest/recon/
mv *.xml ~/pentest/scan/
```

#### B. Report Writing
```bash
# Create report template
cat << EOF > ~/pentest/report/report.md
# Information Gathering Report

## Target Information
- Domain: target.com
- IP Range: 192.168.1.0/24

## Findings
1. Network Information
2. Domain Details
3. Web Technologies
4. Open Ports

## Recommendations
EOF
```

## Praktikum
### 1. Information Collection
- Domain research
- Network scanning
- Web enumeration

### 2. Data Analysis
- Result verification
- Finding correlation
- Risk assessment

### 3. Report Creation
- Data organization
- Finding documentation
- Recommendation writing

## Tugas
1. Lakukan information gathering lengkap
2. Dokumentasikan semua temuan
3. Buat laporan profesional

## Referensi
1. [OSINT Framework](https://osintframework.com/)
2. [Nmap Documentation](https://nmap.org/docs.html)
3. [Information Gathering Guide](https://www.kali.org/docs/usb/kali-linux-live-usb-install/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari konsep vulnerability assessment
2. Siapkan tools scanning
3. Review target systems

*Note: Pastikan semua pengumpulan informasi dilakukan dengan izin yang tepat dan dalam lingkungan yang terkontrol.*
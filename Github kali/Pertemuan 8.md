# Pertemuan 8: Praktikum Web Security

## Apersepsi (15 menit)
Setelah memahami konsep web security dan OWASP Top 10, kita akan mempraktekkan pengujian keamanan web secara langsung. Praktikum ini akan membantu mengidentifikasi dan mengamankan celah keamanan aplikasi web.

## Tujuan Pembelajaran
1. Melakukan web security testing
2. Mengidentifikasi celah keamanan
3. Menggunakan tools testing
4. Menerapkan teknik perbaikan

## Materi

### 1. Persiapan Testing (30 menit)
#### A. Environment Setup
```bash
# Install tools
sudo apt install -y burpsuite zaproxy nikto sqlmap

# Start services
sudo systemctl start postgresql
sudo burpsuite &
```

#### B. Target Configuration
```bash
# Create target file
echo "http://target.com" > targets.txt

# Test connectivity
curl -I http://target.com
ping -c 3 target.com
```

### 2. Information Gathering (45 menit)
#### A. Technology Detection
```bash
# Web technology scan
whatweb -v target.com

# SSL analysis
sslyze target.com

# Header inspection
curl -I target.com
```

#### B. Directory Enumeration
```bash
# Directory scanning
dirb http://target.com

# File discovery
gobuster dir -u target.com -w /usr/share/wordlists/dirb/common.txt

# Backup files
for ext in bak old backup; do
    curl -I target.com/index.php.$ext
done
```

### 3. Vulnerability Testing (45 menit)
#### A. Automated Scanning
```bash
# Nikto scan
nikto -h target.com -Tuning 123bde

# ZAP scan
zap-cli quick-scan target.com

# Store results
mkdir -p ~/websec/{scans,reports}
```

#### B. Manual Testing
```bash
# Test SQL injection
sqlmap -u "target.com/page.php?id=1" --dbs

# XSS testing
curl "target.com/search?q=<script>alert(1)</script>"

# File inclusion
curl "target.com/page.php?file=../../../etc/passwd"
```

### 4. Authentication Testing (45 menit)
#### A. Login Testing
```bash
# Basic auth test
hydra -L users.txt -P pass.txt target.com http-post-form

# Password policy
for pass in password 123456 admin; do
    curl -d "username=admin&password=$pass" target.com/login
done
```

#### B. Session Analysis
```bash
# Get session cookie
curl -c cookies.txt target.com/login

# Test session fixation
curl -b "session=test123" target.com

# Check cookie security
curl -I target.com | grep -i set-cookie
```

### 5. Report Generation (45 menit)
#### A. Evidence Collection
```bash
# Screenshot vulnerable pages
cutycapt --url=target.com --out=vuln.png

# Save responses
curl -D headers.txt target.com
wget -r -l1 target.com
```

#### B. Report Writing
```bash
# Create report structure
cat << EOF > web_security_report.md
# Web Security Assessment Report

## Executive Summary

## Methodology

## Findings
1. SQL Injection
2. XSS Vulnerabilities
3. Authentication Issues
4. Configuration Problems

## Recommendations

## Evidence
EOF
```

## Praktikum
### 1. Tool Usage
- Proxy configuration
- Scanner setup
- Testing tools

### 2. Security Testing
- Authentication testing
- Injection testing
- Configuration review

### 3. Documentation
- Evidence collection
- Finding verification
- Report writing

## Tugas
1. Lakukan web security assessment
2. Identifikasi celah keamanan
3. Buat laporan lengkap

## Referensi
1. [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
2. [Web Security Academy](https://portswigger.net/web-security)
3. [Bug Bounty Methodology](https://github.com/KathanP19/HowToHunt)

## Persiapan Pertemuan Selanjutnya
1. Pelajari konsep network security
2. Siapkan tools jaringan
3. Review protokol jaringan

*Note: Pastikan untuk selalu mendapat izin sebelum melakukan web security testing.*
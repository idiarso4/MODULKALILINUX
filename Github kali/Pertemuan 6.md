# Pertemuan 6: Praktikum Vulnerability Assessment

## Apersepsi (15 menit)
Setelah memahami konsep vulnerability assessment, saatnya kita praktekkan secara langsung. Praktikum ini akan membantu mengidentifikasi dan menganalisis kerentanan sistem secara sistematis.

## Tujuan Pembelajaran
1. Melakukan vulnerability assessment
2. Menggunakan scanner secara efektif
3. Menganalisis hasil scanning
4. Membuat laporan assessment

## Materi

### 1. Persiapan Assessment (30 menit)
#### A. Environment Setup
```bash
# Update tools
sudo apt update
sudo apt install -y nmap nikto openvas

# Check installation
which nmap nikto openvas-check-setup
```

#### B. Target Configuration
```bash
# Create target list
echo "target.com" > targets.txt

# Basic reachability test
ping -c 3 target.com
nmap -sn target.com
```

### 2. Network Assessment (45 menit)
#### A. Port Scanning
```bash
# Quick scan
nmap -F target.com

# Full scan with service detection
nmap -sV -p- target.com

# Vulnerability scripts
nmap --script vuln target.com
```

#### B. Service Enumeration
```bash
# Banner grabbing
nc -v target.com 80
nc -v target.com 443

# Service detection
nmap -sV --version-intensity 5 target.com
```

### 3. Web Application Testing (45 menit)
#### A. Automated Scanning
```bash
# Nikto scan
nikto -h target.com -Tuning 123bde

# SSL testing
sslyze target.com

# Directory scanning
dirb http://target.com
```

#### B. Manual Testing
```bash
# Test HTTP methods
curl -X OPTIONS target.com -i

# Check headers
curl -I target.com

# Test common files
for file in robots.txt .htaccess .git; do
    curl -I target.com/$file
done
```

### 4. System Assessment (45 menit)
#### A. OS Detection
```bash
# OS fingerprinting
nmap -O target.com

# Service fingerprinting
nmap -sV --version-all target.com

# Banner collection
for port in 21 22 25 80 443; do
    nc -v -n -w1 target.com $port
done
```

#### B. Common Vulnerabilities
```bash
# Check known vulnerabilities
searchsploit apache 2.4
searchsploit mysql 5.7

# CVE lookup
curl https://cve.circl.lu/api/search/apache/2.4
```

### 5. Report Generation (45 menit)
#### A. Finding Documentation
```bash
# Create report directory
mkdir -p ~/assessment/{raw,processed,report}

# Collect scan results
cp *_scan.txt ~/assessment/raw/
grep "VULNERABLE" *_scan.txt > ~/assessment/processed/vulns.txt
```

#### B. Report Writing
```bash
# Create report
cat << EOF > ~/assessment/report/report.md
# Vulnerability Assessment Report

## Executive Summary

## Methodology

## Findings
### Critical
### High
### Medium
### Low

## Recommendations

## Appendices
EOF
```

## Praktikum
### 1. Scanner Usage
- Tool configuration
- Scan execution
- Result collection

### 2. Vulnerability Testing
- Network assessment
- Web application testing
- System scanning

### 3. Report Writing
- Finding analysis
- Risk assessment
- Recommendation writing

## Tugas
1. Lakukan full vulnerability assessment
2. Analisis dan verifikasi temuan
3. Buat laporan profesional

## Referensi
1. [Vulnerability Assessment Guide](https://www.kali.org/docs/assessment/)
2. [NIST SP 800-115](https://nvlpubs.nist.gov/nistpubs/Legacy/SP/nistspecialpublication800-115.pdf)
3. [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari konsep web security
2. Siapkan tools web testing
3. Review OWASP Top 10

*Note: Pastikan untuk selalu mendapat izin sebelum melakukan vulnerability assessment.*
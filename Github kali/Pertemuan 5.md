# Pertemuan 5: Konsep Vulnerability Assessment

## Apersepsi (15 menit)
Vulnerability assessment adalah langkah kritis dalam mengidentifikasi celah keamanan sistem. Dengan pemahaman yang baik tentang konsep dan tools yang tepat, kita dapat menemukan dan menganalisis kerentanan secara efektif.

## Tujuan Pembelajaran
1. Memahami konsep dasar vulnerability assessment
2. Mengenal berbagai jenis vulnerability scanner
3. Mempelajari metodologi scanning
4. Menganalisis hasil assessment

## Materi

### 1. Konsep Dasar (30 menit)
#### A. Definisi dan Tujuan
- Pengertian vulnerability
- Tipe-tipe kerentanan
- Risk assessment
- Prioritas penanganan

#### B. Metodologi
```bash
# Membuat struktur project
mkdir -p ~/vulnassess/{scan,report,evidence}

# Membuat checklist
cat << EOF > ~/vulnassess/checklist.txt
1. Information Gathering
2. Service Enumeration
3. Vulnerability Scanning
4. Manual Verification
5. Risk Analysis
6. Documentation
EOF
```

### 2. Tools Scanning (45 menit)
#### A. Network Scanner
```bash
# Nmap vulnerability scripts
ls /usr/share/nmap/scripts/vuln*

# Basic vulnerability scan
nmap -sV --script vuln target.com

# Service detection
nmap -sV --version-intensity 5 target.com
```

#### B. Web Scanner
```bash
# Nikto scan
nikto -h target.com -Tuning 123bde

# OWASP ZAP CLI
zap-cli quick-scan target.com

# Arachni scan
arachni http://target.com
```

### 3. Vulnerability Types (45 menit)
#### A. Common Vulnerabilities
```bash
# Check CVE database
searchsploit apache 2.4

# View vulnerability details
curl https://nvd.nist.gov/vuln/detail/CVE-2021-1234
```

#### B. Risk Categories
```bash
# Create risk matrix
cat << EOF > risk_matrix.md
## Risk Levels
1. Critical  - Immediate action required
2. High      - Urgent attention needed
3. Medium    - Plan required
4. Low       - Monitor and review
EOF
```

### 4. Assessment Process (45 menit)
#### A. Planning
```bash
# Create assessment plan
cat << EOF > assessment_plan.md
1. Scope Definition
2. Tool Selection
3. Timeline Planning
4. Resource Allocation
5. Documentation Requirements
EOF
```

#### B. Execution
```bash
# Basic assessment workflow
nmap -sV target.com > initial_scan.txt
nikto -h target.com > web_scan.txt
sslyze target.com > ssl_scan.txt
```

### 5. Result Analysis (45 menit)
#### A. Finding Classification
```bash
# Sort findings
grep "CRITICAL" *_scan.txt > critical.txt
grep "HIGH" *_scan.txt > high.txt
grep "MEDIUM" *_scan.txt > medium.txt
```

#### B. Report Structure
```bash
# Create report template
cat << EOF > report_template.md
# Vulnerability Assessment Report

## Executive Summary

## Methodology

## Findings
- Critical Vulnerabilities
- High Risk Issues
- Medium Concerns
- Low Risk Items

## Recommendations

## Appendices
EOF
```

## Praktikum
### 1. Scanner Setup
- Tool installation
- Configuration
- Test scanning

### 2. Basic Assessment
- Network scanning
- Service detection
- Vulnerability identification

### 3. Result Analysis
- Finding verification
- Risk assessment
- Report preparation

## Tugas
1. Install vulnerability scanner
2. Lakukan basic assessment
3. Buat laporan temuan

## Referensi
1. [NIST Vulnerability Database](https://nvd.nist.gov/)
2. [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
3. [Common Vulnerability Scoring System](https://www.first.org/cvss/)

## Persiapan Pertemuan Selanjutnya
1. Siapkan environment testing
2. Review vulnerability types
3. Pelajari teknik scanning

*Note: Pastikan untuk selalu mendapatkan izin sebelum melakukan vulnerability assessment.*
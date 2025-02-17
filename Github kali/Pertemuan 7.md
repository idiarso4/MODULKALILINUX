# Pertemuan 7: Pengenalan Web Security

## Apersepsi (15 menit)
Aplikasi web menjadi target utama serangan cyber karena banyaknya data sensitif yang diproses. Memahami keamanan web dan OWASP Top 10 sangat penting untuk melindungi aplikasi web.

## Tujuan Pembelajaran
1. Memahami konsep web security
2. Mengenal OWASP Top 10
3. Mempelajari tools web testing
4. Mengidentifikasi celah keamanan web

## Materi

### 1. Konsep Web Security (30 menit)
#### A. Dasar Web Security
- HTTP/HTTPS
- Web architecture
- Attack vectors
- Defense in depth

#### B. OWASP Top 10
```bash
# Access OWASP documentation
xdg-open https://owasp.org/Top10/

# Download resources
wget https://owasp.org/www-pdf-archive/OWASP_Top_10-2021_en.pdf

# View common vulnerabilities
cat << EOF > vulns.txt
1. Broken Access Control
2. Cryptographic Failures
3. Injection
4. Insecure Design
5. Security Misconfiguration
EOF
```

### 2. Tools Web Testing (45 menit)
#### A. Proxy Setup
```bash
# Install tools
sudo apt install -y burpsuite zaproxy

# Configure browser proxy
firefox about:preferences
# Set proxy: 127.0.0.1:8080

# Test proxy
curl -x http://127.0.0.1:8080 http://example.com
```

#### B. Scanner Configuration
```bash
# Nikto setup
nikto -update
nikto -list-plugins

# ZAP CLI
zap-cli --help
zap-cli start
```

### 3. Common Vulnerabilities (45 menit)
#### A. SQL Injection
```bash
# Basic tests
curl "target.com/page.php?id=1'"
curl "target.com/page.php?id=1 OR 1=1"

# SQLMap basic
sqlmap -u "target.com/page.php?id=1" --dbs
```

#### B. XSS Testing
```bash
# Reflected XSS test
curl "target.com/search?q=<script>alert(1)</script>"

# Stored XSS test
curl -X POST target.com/comment \
  -d "content=<script>alert(1)</script>"
```

### 4. Security Headers (45 menit)
#### A. Header Analysis
```bash
# Check security headers
curl -I https://target.com

# Test CORS
curl -H "Origin: https://evil.com" \
  -I https://target.com

# SSL/TLS check
sslyze target.com
```

#### B. Content Security Policy
```bash
# Check CSP
curl -I target.com | grep -i content-security-policy

# Test CSP bypass
curl target.com -H "Content-Security-Policy: default-src 'none'"
```

### 5. Authentication Testing (45 menit)
#### A. Password Testing
```bash
# Basic auth test
curl -u admin:password target.com

# Brute force protection
for i in {1..5}; do
    curl -u admin:wrong target.com
done
```

#### B. Session Analysis
```bash
# Get cookies
curl -c cookies.txt target.com

# Test session fixation
curl -b "session=test" target.com

# Check cookie flags
curl -I target.com | grep -i set-cookie
```

## Praktikum
### 1. Tool Setup
- Proxy configuration
- Scanner installation
- Browser setup

### 2. Basic Testing
- Header analysis
- Cookie inspection
- Form testing

### 3. Vulnerability Scanning
- Automated scans
- Manual verification
- Result analysis

## Tugas
1. Setup testing environment
2. Lakukan basic web testing
3. Dokumentasikan temuan

## Referensi
1. [OWASP Top 10](https://owasp.org/Top10/)
2. [Web Security Academy](https://portswigger.net/web-security)
3. [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)

## Persiapan Pertemuan Selanjutnya
1. Pelajari teknik web testing lanjutan
2. Siapkan target untuk praktikum
3. Review vulnerability types

*Note: Pastikan untuk selalu mendapat izin sebelum melakukan web security testing.*
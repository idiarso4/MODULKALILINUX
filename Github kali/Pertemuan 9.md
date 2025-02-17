# Pertemuan 9: Network Security

## Apersepsi (15 menit)
Jaringan komputer adalah tulang punggung komunikasi modern. Memahami keamanan jaringan sangat penting untuk melindungi sistem dari berbagai ancaman network-based dan memastikan keamanan data yang ditransmisikan.

## Tujuan Pembelajaran
1. Memahami konsep network security
2. Mengenal jenis-jenis serangan jaringan
3. Mempelajari tools network security
4. Mengidentifikasi ancaman jaringan

## Materi

### 1. Konsep Network Security (30 menit)
#### A. Dasar Network Security
- Network layers
- Protocol security
- Attack vectors
- Defense mechanisms

#### B. Common Threats
```bash
# Create threat list
cat << EOF > threats.md
1. Man-in-the-Middle
2. ARP Spoofing
3. DNS Poisoning
4. DDoS Attacks
5. Port Scanning
EOF

# View network statistics
netstat -tuln
ss -tuln
```

### 2. Network Analysis Tools (45 menit)
#### A. Packet Analysis
```bash
# Install tools
sudo apt install -y wireshark tcpdump nmap

# Capture traffic
tcpdump -i any -w capture.pcap

# Analyze with Wireshark
wireshark capture.pcap
```

#### B. Network Mapping
```bash
# Network discovery
nmap -sn 192.168.1.0/24

# Port scanning
nmap -p- target.com

# Service detection
nmap -sV target.com
```

### 3. Protocol Security (45 menit)
#### A. SSL/TLS Analysis
```bash
# SSL testing
sslyze target.com

# Certificate check
openssl s_client -connect target.com:443

# Protocol support
nmap --script ssl-enum-ciphers target.com
```

#### B. Network Services
```bash
# Service enumeration
nmap -sV --version-all target.com

# Banner grabbing
nc -v target.com 80
nc -v target.com 443
```

### 4. Network Defense (45 menit)
#### A. Firewall Configuration
```bash
# View current rules
sudo iptables -L

# Basic protection
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -P INPUT DROP
```

#### B. IDS/IPS Setup
```bash
# Snort configuration
sudo snort -T -c /etc/snort/snort.conf

# View rules
ls /etc/snort/rules/
grep "alert" /etc/snort/rules/*.rules
```

### 5. Network Monitoring (45 menit)
#### A. Traffic Analysis
```bash
# Monitor bandwidth
iftop -i eth0

# Process connections
nethogs eth0

# Network statistics
iptraf-ng
```

#### B. Log Analysis
```bash
# System logs
tail -f /var/log/syslog

# Authentication logs
tail -f /var/log/auth.log

# Network logs
tail -f /var/log/kern.log
```

## Praktikum
### 1. Tool Usage
- Packet capture
- Traffic analysis
- Network mapping

### 2. Security Analysis
- Protocol testing
- Service scanning
- Vulnerability detection

### 3. Defense Setup
- Firewall rules
- IDS configuration
- Log monitoring

## Tugas
1. Lakukan network assessment
2. Konfigurasi basic security
3. Buat laporan analisis

## Referensi
1. [Network Security Guide](https://www.sans.org/security-resources/tcpip.pdf)
2. [Wireshark Documentation](https://www.wireshark.org/docs/)
3. [Snort Manual](https://www.snort.org/documents)

## Persiapan Pertemuan Selanjutnya
1. Pelajari praktik network security
2. Siapkan tools monitoring
3. Review defense mechanisms

*Note: Pastikan untuk selalu mendapat izin sebelum melakukan network security testing.*
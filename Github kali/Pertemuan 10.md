# Pertemuan 10: Praktikum Network Security

## Apersepsi (15 menit)
Setelah memahami konsep network security, kita akan mempraktekkan pengujian dan pengamanan jaringan secara langsung. Praktikum ini akan membantu memahami cara mengidentifikasi dan mengatasi ancaman jaringan.

## Tujuan Pembelajaran
1. Melakukan network assessment
2. Mengamankan jaringan
3. Menggunakan tools monitoring
4. Menerapkan defense mechanism

## Materi

### 1. Persiapan Assessment (30 menit)
#### A. Tool Setup
```bash
# Install tools
sudo apt install -y wireshark tcpdump nmap snort

# Start services
sudo systemctl start snort
sudo wireshark &
```

#### B. Network Configuration
```bash
# Check interfaces
ip addr
ifconfig

# Test connectivity
ping -c 3 target.com
traceroute target.com
```

### 2. Network Scanning (45 menit)
#### A. Host Discovery
```bash
# Network sweep
nmap -sn 192.168.1.0/24

# ARP scan
arp-scan --localnet

# Host enumeration
nbtscan 192.168.1.0/24
```

#### B. Port Analysis
```bash
# Quick scan
nmap -F target.com

# Full port scan
nmap -p- target.com

# Service detection
nmap -sV -p80,443,22 target.com
```

### 3. Traffic Analysis (45 menit)
#### A. Packet Capture
```bash
# Capture traffic
tcpdump -i any -w capture.pcap

# Filter specific traffic
tcpdump -i any 'port 80 or port 443'

# Analyze with Wireshark
tshark -r capture.pcap
```

#### B. Protocol Analysis
```bash
# HTTP traffic
tcpdump -i any 'tcp port 80' -A

# DNS queries
tcpdump -i any 'udp port 53'

# SSL/TLS analysis
ssldump -i any
```

### 4. Network Defense (45 menit)
#### A. Firewall Setup
```bash
# Basic rules
sudo iptables -A INPUT -p tcp --dport 22 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 80 -j ACCEPT
sudo iptables -A INPUT -p tcp --dport 443 -j ACCEPT

# Default policies
sudo iptables -P INPUT DROP
sudo iptables -P FORWARD DROP
```

#### B. IDS Configuration
```bash
# Test Snort config
sudo snort -T -c /etc/snort/snort.conf

# Start monitoring
sudo snort -A console -q -c /etc/snort/snort.conf

# Check logs
tail -f /var/log/snort/alert
```

### 5. Security Monitoring (45 menit)
#### A. Network Monitoring
```bash
# Bandwidth monitoring
iftop -i eth0

# Connection tracking
netstat -tunap
ss -tunap

# Process monitoring
lsof -i
```

#### B. Log Analysis
```bash
# System logs
tail -f /var/log/syslog

# Authentication logs
tail -f /var/log/auth.log

# Create log summary
grep "Failed password" /var/log/auth.log | awk '{print $11}' | sort | uniq -c
```

## Praktikum
### 1. Network Assessment
- Host discovery
- Service detection
- Traffic analysis

### 2. Defense Implementation
- Firewall configuration
- IDS setup
- Log monitoring

### 3. Security Testing
- Attack detection
- Defense verification
- Incident response

## Tugas
1. Lakukan network assessment
2. Implementasi security controls
3. Buat monitoring system

## Referensi
1. [Wireshark User Guide](https://www.wireshark.org/docs/)
2. [Snort Documentation](https://www.snort.org/documents)
3. [Iptables Tutorial](https://www.frozentux.net/iptables-tutorial/iptables-tutorial.html)

## Persiapan Pertemuan Selanjutnya
1. Pelajari project requirements
2. Siapkan testing environment
3. Review semua materi

*Note: Pastikan untuk selalu mendapat izin sebelum melakukan network security testing.*
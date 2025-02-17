# Modul 1: Pengenalan Ethical Hacking dan Keamanan Siber

## Deskripsi Modul
Modul ini memberikan pengenalan komprehensif tentang ethical hacking dan keamanan siber. Peserta akan mempelajari konsep dasar, metodologi, aspek legal dan etika, serta melakukan hands-on practice dengan tools dasar dalam Kali Linux.

## Tujuan Pembelajaran
Setelah menyelesaikan modul ini, peserta diharapkan dapat:
1. Memahami konsep dasar keamanan siber dan CIA Triad
2. Menjelaskan perbedaan ethical hacking dan cyber crime
3. Mengidentifikasi berbagai jenis ancaman keamanan
4. Menerapkan metodologi ethical hacking
5. Menggunakan tools dasar dalam Kali Linux
6. Memahami aspek legal dan etika dalam ethical hacking

## Durasi
- Total: 6 jam
- Teori: 3 jam
- Praktikum: 3 jam

## Prasyarat
1. Pengetahuan Dasar:
   - Sistem operasi komputer
   - Jaringan komputer dasar
   - Command line interface

2. Perangkat:
   - Laptop/PC dengan minimal:
     * Processor: Intel Core i5/AMD Ryzen 5
     * RAM: 8GB
     * Storage: 256GB
   - Koneksi internet stabil

## Materi Pembelajaran

### BAB 1: Konsep Dasar Keamanan Siber
#### 1.1 CIA Triad
##### 1.1.1 Confidentiality (Kerahasiaan)
- Definisi:
  * Perlindungan terhadap akses informasi tidak sah
  * Menjaga privasi data sensitif
  * Kontrol akses informasi

- Implementasi:
  * Enkripsi data
  * Access control lists (ACL)
  * Authentication mechanisms
  * Data classification

- Contoh Kasus:
  * Medical records protection
  * Financial data security
  * Intellectual property protection

##### 1.1.2 Integrity (Integritas)
- Definisi:
  * Akurasi dan konsistensi data
  * Perlindungan dari modifikasi tidak sah
  * Validasi perubahan

- Implementasi:
  * Hashing
  * Digital signatures
  * Checksums
  * Version control

- Contoh Kasus:
  * Banking transactions
  * Software updates
  * Legal documents

##### 1.1.3 Availability (Ketersediaan)
- Definisi:
  * Akses ke sistem dan data saat dibutuhkan
  * Kehandalan layanan
  * Business continuity

- Implementasi:
  * Redundancy
  * Backup systems
  * Disaster recovery
  * Load balancing

- Contoh Kasus:
  * E-commerce platforms
  * Healthcare systems
  * Emergency services

#### 1.2 AAA Framework
##### 1.2.1 Authentication
- Metode:
  * Password-based
  * Biometric
  * Token-based
  * Multi-factor

- Best Practices:
  * Strong password policies
  * Regular credential rotation
  * Failed attempt lockouts
  * Session management

##### 1.2.2 Authorization
- Konsep:
  * Role-based access control
  * Attribute-based access control
  * Mandatory access control
  * Discretionary access control

- Implementasi:
  * Permission matrices
  * Access levels
  * Group policies
  * Least privilege principle

##### 1.2.3 Accounting
- Komponen:
  * Log generation
  * Audit trails
  * Monitoring systems
  * Report generation

- Best Practices:
  * Regular log review
  * Secure log storage
  * Alert mechanisms
  * Compliance reporting

### BAB 2: Ancaman Keamanan
#### 2.1 Jenis Ancaman
##### 2.1.1 Malware
- Virus:
  * File infectors
  * Boot sector viruses
  * Macro viruses
  * Polymorphic viruses

- Worms:
  * Network worms
  * Email worms
  * IM worms
  * File-sharing worms

- Trojans:
  * Remote access trojans
  * Banking trojans
  * Backdoor trojans
  * Downloader trojans

- Ransomware:
  * Crypto ransomware
  * Locker ransomware
  * Scareware
  * Doxware

##### 2.1.2 Social Engineering
- Phishing:
  * Email phishing
  * Spear phishing
  * Whaling
  * Vishing

- Pretexting:
  * Identity impersonation
  * Authority abuse
  * Emergency scenarios
  * Technical support scams

##### 2.1.3 Network Attacks
- DDoS:
  * Volume-based attacks
  * Protocol attacks
  * Application layer attacks
  * Amplification attacks

- Man-in-the-Middle:
  * ARP spoofing
  * DNS spoofing
  * SSL stripping
  * Session hijacking

### BAB 3: Metodologi Ethical Hacking
#### 3.1 Planning dan Reconnaissance
##### 3.1.1 Scope Definition
- Project boundaries
- Target systems
- Timeframes
- Deliverables

##### 3.1.2 Information Gathering
- Passive reconnaissance
- Active reconnaissance
- OSINT techniques
- Target profiling

#### 3.2 Scanning dan Enumeration
##### 3.2.1 Network Scanning
```bash
# Basic network scanning
nmap -sn 192.168.1.0/24    # Network discovery
nmap -sS -sV target        # Service detection
nmap -A target             # Aggressive scan
```

##### 3.2.2 Vulnerability Scanning
```bash
# Basic vulnerability scanning
nikto -h target
openvas-start
nmap --script vuln target
```

#### 3.3 Gaining Access
##### 3.3.1 Exploitation Methods
- Password attacks
- Vulnerability exploitation
- Social engineering
- Application attacks

##### 3.3.2 Post Exploitation
- Privilege escalation
- Data extraction
- Persistence
- Lateral movement

### BAB 4: Hands-on Lab
#### 4.1 Kali Linux Setup
##### 4.1.1 VirtualBox Installation
```bash
# Windows installation
choco install virtualbox

# Linux installation
sudo apt install virtualbox
```

##### 4.1.2 Kali Linux Installation
1. Download ISO:
   - Visit kali.org/downloads
   - Choose appropriate version
   - Verify checksums

2. VM Configuration:
   - 2 CPU cores
   - 4GB RAM minimum
   - 80GB storage
   - NAT networking

#### 4.2 Basic Tools Usage
##### 4.2.1 System Updates
```bash
# System update commands
sudo apt update
sudo apt upgrade
sudo apt dist-upgrade
```

##### 4.2.2 Tool Installation
```bash
# Essential tools
sudo apt install nmap wireshark metasploit-framework
sudo apt install burpsuite nikto dirb
```

## Latihan dan Tugas
### A. Quiz Teori
1. Jelaskan komponen CIA Triad dan berikan contoh implementasinya.
2. Apa perbedaan utama antara ethical hacking dan cyber crime?
3. Sebutkan dan jelaskan 3 jenis malware beserta cara kerjanya.

### B. Praktikum
1. Setup Environment:
   - Install VirtualBox
   - Create Kali Linux VM
   - Configure networking

2. Tool Exploration:
   - Update system
   - Install basic tools
   - Test network connectivity
   - Perform basic scanning

### C. Project
Buatlah laporan reconnaissance terhadap sistem yang telah ditentukan, mencakup:
1. Network mapping
2. Service enumeration
3. Vulnerability identification
4. Risk assessment

## Referensi
### Buku
1. "CEH Certified Ethical Hacker Study Guide"
2. "The Basics of Hacking and Penetration Testing"
3. "Network Security Assessment"

### Online Resources
1. [Kali Linux Documentation](https://www.kali.org/docs/)
2. [OWASP Top Ten](https://owasp.org/www-project-top-ten/)
3. [Exploit Database](https://www.exploit-db.com/)

### Video Tutorials
1. Cybrary Ethical Hacking Course
2. INE Security Course
3. HackerSploit YouTube Channel

## Evaluasi
### Kriteria Penilaian
1. Pemahaman Teori (30%):
   - Quiz: 15%
   - Diskusi: 15%

2. Praktikum (40%):
   - Lab completion: 20%
   - Tool mastery: 20%

3. Project (30%):
   - Technical accuracy: 15%
   - Documentation: 15%

### Rubrik Penilaian
#### Teori
| Kriteria | Excellent (90-100) | Good (80-89) | Fair (70-79) | Poor (<70) |
|----------|-------------------|--------------|--------------|------------|
| Pemahaman Konsep | Menunjukkan pemahaman mendalam | Pemahaman baik dengan sedikit kesalahan | Pemahaman dasar dengan beberapa kesalahan | Kurang pemahaman |
| Aplikasi | Dapat mengaplikasikan konsep dengan tepat | Aplikasi baik dengan sedikit kesalahan | Aplikasi dasar dengan beberapa kesalahan | Kesulitan mengaplikasikan |

#### Praktikum
| Kriteria | Excellent (90-100) | Good (80-89) | Fair (70-79) | Poor (<70) |
|----------|-------------------|--------------|--------------|------------|
| Tool Usage | Mahir menggunakan tools | Penggunaan baik dengan sedikit bantuan | Penggunaan dasar dengan bantuan | Kesulitan menggunakan tools |
| Problem Solving | Dapat menyelesaikan masalah secara mandiri | Penyelesaian baik dengan sedikit bantuan | Penyelesaian dengan bantuan | Kesulitan menyelesaikan masalah |

## Glosarium
- **CIA Triad**: Framework keamanan yang terdiri dari Confidentiality, Integrity, dan Availability
- **Ethical Hacking**: Proses pengujian keamanan sistem dengan izin legal
- **Malware**: Software yang dirancang untuk merusak sistem
- **Penetration Testing**: Pengujian keamanan sistem dengan simulasi serangan
- **Social Engineering**: Manipulasi psikologis untuk mendapatkan informasi
- **Vulnerability**: Kelemahan dalam sistem yang dapat dieksploitasi

## Appendix
### A. Command Cheatsheet
```bash
# Network Commands
ifconfig                # Network interface configuration
ip addr                 # IP address information
netstat -tuln          # Active connections
ping host              # Test connectivity

# Security Tools
nmap -sV target        # Service version detection
nikto -h target        # Web server scanning
dirb http://target     # Directory busting
wireshark              # Network packet analysis
```

### B. Troubleshooting Guide
1. VM Issues:
   - Check hardware virtualization
   - Verify resource allocation
   - Update VirtualBox

2. Network Issues:
   - Verify network adapter
   - Check IP configuration
   - Test connectivity

3. Tool Issues:
   - Update package lists
   - Check dependencies
   - Verify permissions

### C. Additional Resources
1. Practice Platforms:
   - HackTheBox
   - TryHackMe
   - VulnHub

2. Security Tools:
   - Metasploit
   - Burp Suite
   - OWASP ZAP

3. Learning Resources:
   - Security blogs
   - CTF platforms
   - Online courses

# Pertemuan 12: Presentasi Project dan Evaluasi

## Apersepsi (15 menit)
Presentasi project akhir merupakan kesempatan untuk menunjukkan hasil pengujian keamanan yang telah dilakukan. Evaluasi akan membantu mengidentifikasi kekuatan dan area yang perlu ditingkatkan.

## Tujuan Pembelajaran
1. Mempresentasikan hasil project
2. Mengevaluasi pembelajaran
3. Membahas temuan keamanan
4. Memberikan rekomendasi

## Materi

### 1. Persiapan Presentasi (30 menit)
#### A. Slide Preparation
```bash
# Create presentation directory
mkdir -p ~/presentation/{slides,demo,evidence}

# Convert report to slides
pandoc -t beamer report.md -o slides.pdf

# Check content
ls -R ~/presentation/
```

#### B. Demo Setup
```bash
# Test tools
which nmap wireshark metasploit-framework

# Check connectivity
ping -c 3 target.com
nmap -sn target.com

# Prepare screenshots
scrot -h
```

### 2. Project Presentation (45 menit)
#### A. Executive Summary
```bash
# Generate summary
cat << EOF > summary.md
# Project Summary

## Scope
- Network assessment
- Web application testing
- Security analysis

## Key Findings
1. Critical vulnerabilities
2. High-risk issues
3. Security recommendations

## Impact Assessment
- Business impact
- Technical risks
- Mitigation steps
EOF
```

#### B. Technical Demo
```bash
# Network scan demo
nmap -sV target.com

# Web vulnerability demo
nikto -h target.com

# Exploitation demo
msfconsole -q -x "use exploit/multi/handler; exit"
```

### 3. Evaluasi Pembelajaran (45 menit)
#### A. Knowledge Review
```bash
# Create checklist
cat << EOF > review.md
# Learning Objectives

1. Information Gathering
   - OSINT techniques
   - Network mapping
   - Service enumeration

2. Vulnerability Assessment
   - Scanner usage
   - Manual testing
   - Result analysis

3. Security Implementation
   - Defense setup
   - Monitoring
   - Incident response
EOF
```

#### B. Skill Assessment
```bash
# Tool proficiency
for tool in nmap nikto wireshark; do
    which $tool
    $tool --version
done

# Check configurations
ls -la ~/.msf4/
ls -la ~/.zap/
```

### 4. Feedback Session (45 menit)
#### A. Project Review
```bash
# Analyze findings
grep "Critical" report.md
grep "High" report.md

# Count vulnerabilities
cat << EOF > stats.md
# Project Statistics

- Critical findings: 5
- High-risk issues: 8
- Medium concerns: 12
- Low-risk items: 15

Total vulnerabilities: 40
EOF
```

#### B. Improvement Areas
```bash
# Create improvement plan
cat << EOF > improvements.md
# Areas for Improvement

1. Technical Skills
   - Advanced exploitation
   - Custom tool development
   - Automation skills

2. Documentation
   - Report writing
   - Evidence collection
   - Finding classification

3. Project Management
   - Time management
   - Team coordination
   - Resource allocation
EOF
```

### 5. Future Planning (45 menit)
#### A. Career Development
```bash
# Create roadmap
cat << EOF > career_path.md
# Professional Development

1. Certifications
   - CompTIA Security+
   - CEH
   - OSCP
   - CISSP

2. Skills Enhancement
   - Reverse engineering
   - Malware analysis
   - Cloud security
   - Mobile security

3. Project Portfolio
   - CTF participation
   - Bug bounty
   - Open source contribution
EOF
```

#### B. Continuous Learning
```bash
# Learning resources
cat << EOF > resources.md
# Learning Resources

1. Online Platforms
   - HackTheBox
   - TryHackMe
   - VulnHub

2. Communities
   - Local security groups
   - Online forums
   - Professional networks

3. Practice Labs
   - Home lab setup
   - Virtual environments
   - Cloud labs
EOF
```

## Praktikum
### 1. Presentation
- Report overview
- Technical demo
- Q&A session

### 2. Evaluation
- Knowledge check
- Skill assessment
- Feedback review

### 3. Planning
- Career planning
- Skill development
- Continuous learning

## Tugas
1. Finalize project report
2. Deliver presentation
3. Create improvement plan

## Referensi
1. [Presentation Skills](https://www.sans.org/blog/presenting-like-a-pro/)
2. [Report Writing](https://www.offensive-security.com/reports/sample-penetration-testing-report.pdf)
3. [Career Development](https://pauljerimy.com/security-certification-roadmap/)

## Persiapan Selanjutnya
1. Review certification paths
2. Plan skill development
3. Join security communities

*Note: Gunakan feedback dan evaluasi sebagai panduan untuk pengembangan skill selanjutnya.*
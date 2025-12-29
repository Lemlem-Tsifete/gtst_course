
---

# Kali Linux Security Assessment Cheat Sheet

## 🐧 Overview

- **Operating System:** Kali Linux (Debian-based).
    
- **Desktop Environment:** GNOME (Customizable and modern).
    
- **Legacy:** Formerly known as **BackTrack**.
    

---

## 🛠️ Tool Categories & Key Applications

### 1. Information Gathering (OSINT)

Tools for mapping network infrastructure and identifying targets.

- **Nmap:** Network discovery and security auditing.
    
- **Maltego:** Link analysis and data mining.
    
- **Recon-ng:** Web-based open-source intelligence framework.
    

### 2. Vulnerability Analysis

Identifying security flaws in systems.

- **Nikto:** Comprehensive web server scanner.
    
- **Nmap (NSE Scripts):** Using the Nmap Scripting Engine to find vulnerabilities.
    

### 3. Web Application Analysis

Testing websites for bugs and exploits.

- **Burp Suite:** The industry standard for web proxying and testing.
    
- **SQLmap:** Automated SQL injection and database takeover.
    
- **WPScan:** Vulnerability scanner for WordPress sites.
    

### 4. Database Assessment

- **SQLmap:** (Primary tool) Detects and exploits SQLi.
    
- **jSQL Injection:** A Java application for automatic database injection.
    

### 5. Password Attacks

Cracking hashes and brute-forcing logins.

- **John the Ripper:** Powerful password cracker for local hashes.
    
- **Hashcat:** The world's fastest CPU/GPU-based password recovery tool.
    
- **Hydra:** Very fast network login cracker (SSH, FTP, etc.).
    

### 6. Wireless Attacks

Auditing Wi-Fi network security.

- **Aircrack-ng:** Suite of tools for Wi-Fi auditing (WEP/WPA cracking).
    
- **Wifite:** Automated wireless attack tool.
    
- **Reaver:** Brute-force attack against WPS.
    

### 7. Reverse Engineering

Analyzing compiled code.

- **Ghidra:** NSA's open-source reverse engineering framework.
    
- **Apktool:** Tool for reverse engineering Android apps.
    

### 8. Exploitation Tools

- **Metasploit:** The world's most used penetration testing framework.
    

### 9. Sniffing & Spoofing

Intercepting and manipulating network traffic.

- **Wireshark:** Deep inspection of network protocols.
    
- **Ettercap/Bettercap:** Tools for Man-In-The-Middle (MITM) attacks.
    

### 10. Post Exploitation

Maintaining access and escalating privileges.

- **Powershell Empire:** A post-exploitation framework.
    
- **NetExec (formerly CrackMapExec):** Post-exploitation for Active Directory.
    

### 11. Social Engineering

Psychological manipulation to gain information.

- **SET (Social-Engineer Toolkit):** Standard framework for phishing and website cloning.
    
- **Wifiphisher:** Rogue Access Point framework for Wi-Fi phishing.
    

---

## 🖥️ System Management & Common Apps

### System Services

Control background services using these commands:

- `sudo systemctl start beef-xss` / `stop`
    
- `sudo systemctl start postgresql` (Required for Metasploit)
    

### Usually Used Applications

- **Firefox ESR:** Default browser for web testing.
    
- **Visual Studio Code / Mousepad:** For script editing.
    
- **Qterminal:** The advanced default terminal.
    

---

## 🔑 Essential Commands

|**Command**|**Description**|
|---|---|
|`sudo su`|Switch to the **root** user (full system administrative access).|
|`sudo apt update && sudo apt upgrade`|Keep the system and tools up to date.|
|`ip a`|Check your current IP address and network interfaces.|
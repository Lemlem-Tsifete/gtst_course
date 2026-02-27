# 🛡️ DNS Enumeration & OSINT Reconnaissance Guide

## 🔍 DNS ENUMERATION
*DNS enumeration is the process of locating all DNS servers and their records for an organization. This reveals infrastructure footprint and security configurations.*

### 1. Dig Commands (Domain Information Groper)
| Command | Purpose |
| :--- | :--- |
| `dig` | Show usage, version, and available flags for the tool. |
| `dig <domain>` | **Default Query:** Retrieve the IPv4 (A) record for a domain. |
| `dig <domain> MX` | **Mail Recon:** Find mail servers to identify email providers (e.g., Google/Outlook). |
| `dig <domain> TXT` | **Security Audit:** Check for SPF, DKIM, and DMARC records used for email security. |
| `dig <domain> NS` | **Authority:** Identify which servers are the "source of truth" for the domain. |
| `dig @<server> <domain>` | **Targeted Query:** Query a specific DNS server to see if it provides different info. |

### 2. Nslookup Commands
| Command | Purpose |
| :--- | :--- |
| `nslookup <domain>` | Basic lookup to map a hostname to an IP address. |
| `type=MX <domain>` | Identify servers responsible for receiving email for the domain. |
| `type=NS <domain>` | Discover the authoritative Name Servers. |
| `nslookup -type=TXT <domain>` | Find verification strings and authorized mail senders. |
| `nslookup <domain> <server>` | Test how a specific DNS server responds to a query. |

---

## 🚩 ZONE TRANSFER ATTACK (AXFR)
*A Zone Transfer (AXFR) is intended for replicating DNS databases between servers. If misconfigured, an attacker can download the entire list of hosts.*

### Execution Commands
* **dig:** `dig @ns1.example.com example.com AXFR`
  * *Purpose:* Requests a full copy of the zone file from the specific vulnerable nameserver.
* **nslookup:** `nslookup -type=AXFR example.com ns1.example.com`
  * *Purpose:* Uses the interactive nslookup tool to attempt the same full database dump.

### Why This Matters:
* **Information Disclosure:** Reveals every internal/external record, including hidden dev or staging sites.
* **Network Mapping:** Exposes the internal network structure without requiring brute force.
* **Stealth:** Provides a complete map of the target in a single query.



---

## 🛠️ SUBDOMAIN ENUMERATION TOOLS

### Subfinder (Passive Recon)
| Command | Purpose |
| :--- | :--- |
| `subfinder -d <domain>` | **Standard Recon:** Fast discovery of subdomains using passive sources. |
| `subfinder -d <domain> -o <file>` | **Reporting:** Save results for use in other tools like Nmap. |
| `subfinder -d <domain> -all` | **Deep Dive:** Use every available source (API-based) for maximum coverage. |
| `subfinder -d <domain> -silent` | **Automation:** Clean output (names only) for piping into other scripts. |

### Amass (Advanced Intel)
| Command | Purpose |
| :--- | :--- |
| `amass enum -d <domain>` | **Asset Discovery:** Map the target’s attack surface. |
| `amass enum -passive -d <domain>` | **Stealth:** Gather data from public logs without touching the target. |
| `amass enum -active -d <domain>` | **Verification:** Interact with DNS servers to confirm subdomains exist. |
| `amass intel -d <domain>` | **Infrastructure:** Discover associated IP ranges and ASN numbers. |



---

## 🌐 INFRASTRUCTURE & EMAIL OSINT

### Shodan (Device Search)
* `shodan domain <domain>`: **Asset Inventory:** See all IPs and ports linked to the domain.
* `shodan host <ip>`: **Vulnerability Check:** See open ports and known vulnerabilities for a specific IP.
* `shodan search "<query>"`: **Targeting:** Find specific software versions or exposed services (e.g., `proftpd`).

### h8mail (Credential Hunting)
* `h8mail -t <domain>`: **Breach Discovery:** Find leaked email addresses belonging to a company.
* `h8mail -t <email>`: **Password Recon:** Check if a specific user's password has been leaked in a breach.
* `h8mail -t <target> -j`: **Data Integration:** Export results in JSON for data analysis.

### theHarvester (Public Intelligence)
* `theHarvester -d <domain> -b all`: **Broad Recon:** Scrape Google, Bing, and others for leaked info.
* `theHarvester -d <domain> -b linkedin`: **Social Engineering:** Find employee names and titles for phishing.

---
**Security Note:** Always verify discovered info. OSINT data can be old or "sinkholed."
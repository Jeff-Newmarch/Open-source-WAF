# Open-Source Web Application Firewall (WAF)

## 🚀 Project Overview

This project aims to develop a custom Web Application Firewall (WAF) using **ModSecurity** to detect and block common web attacks.  
Our goal is to enhance the security of web applications by implementing and customizing the **OWASP Core Rule Set (CRS)** to mitigate threats like **SQL Injection**, **Cross-Site Scripting (XSS)**, and **Broken Authentication**.

---

## 📌 Features

- ✅ **ModSecurity Setup** – Installed and configured as a WAF  
- ✅ **OWASP CRS Integration** – Implemented default rules for security  
- ✅ **Ubuntu VM Deployment** – Running the WAF on a virtualized Linux environment  
- ✅ **GitHub Version Control** – Tracking project updates and changes  
- ✅ **Firewall Configurations** – Basic setup using `iptables` / `firewalld`  
- ✅ **Future Enhancements** – Custom rule modifications and extended security testing  

---

## 🔧 Technologies Used

- **ModSecurity** – Open-source WAF for HTTP request filtering  
- **OWASP Core Rule Set (CRS)** – Predefined security rules for common threats  
- **Ubuntu (Linux OS)** – Deployment environment for the WAF  
- **Apache/Nginx** – Web servers to integrate with ModSecurity  
- **iptables / firewalld** – Basic firewall configuration  
- **Git & GitHub** – Version control and collaboration  

---

## 📦 Installation

### 🔹 Requirements

Before starting the installation, ensure you have the following:

- **ModSecurity** installed (we used an Apache Web Server)  
- **Ubuntu** environment  
- **Sudo** privileges  
- **OWASP Core Rule Set**  
  If the rule set is already installed, the process becomes easier.  
  However, full installation instructions are available in our repository under `docs/INSTALL.md`, or you can refer to the official [OWASP CRS documentation](https://coreruleset.org/installation/) for the extended setup guide.

---

### 🧱 Installation Process

To use our custom version of the ModSecurity WAF:

1. Download the following files from our GitHub repository:
   - `custom-rules.conf`  
   - `common-passwords.txt`

2. Place them into the appropriate directories:
   - `custom-rules.conf` → inside the **rules** folder of the OWASP CRS setup  
   - `common-passwords.txt` → in the **parent directory** of the rules folder  

3. Assign the correct ownership and permissions:

```bash
sudo chown www-data:www-data custom-rules.conf
sudo chown www-data:www-data common-passwords.txt
sudo chmod 644 custom-rules.conf
sudo chmod 644 common-passwords.txt

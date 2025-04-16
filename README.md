Open-Source Web Application Firewall (WAF)
🚀 Project Overview
This project aims to develop a custom Web Application Firewall (WAF) using ModSecurity to detect and block common web attacks. Our goal is to enhance the security of web applications by implementing and customizing the OWASP Core Rule Set (CRS) to mitigate threats like SQL Injection, Cross-Site Scripting (XSS), and Broken Authentication.

📌 Features
✔️ ModSecurity Setup – Installed and configured as a WAF
✔️ OWASP CRS Integration – Implementing default rules for security
✔️ Ubuntu VM Deployment – Running the WAF on a virtualized Linux environment
✔️ GitHub Version Control – Tracking project updates and changes
✔️ Firewall Configurations – Basic setup using iptables/firewalld
✔️ Future Enhancements – Custom rule modifications and security testing

🛠 Technologies Used
ModSecurity – Open-source WAF for HTTP request filtering
OWASP Core Rule Set (CRS) – Predefined security rules for common threats
Ubuntu (Linux OS) – Deployment environment for the WAF
Apache/Nginx – Web servers to integrate with ModSecurity
iptables/firewalld – Basic firewall configuration
Git & GitHub – Version control and collaboration

📦 Installation
Requirements
Before starting installation make sure that you have the following:
- ModSecurity Installed (We used an Apache Web Server)
- Ubuntu environment
- Sudo privileges
-OWASP Core Rule Set (If you have the rule set installed already it makes the process easier. However the instructions to install the core rule set is in our repository under the name INSTALL.md in the docs folder or you can go directly to the OWASP Core Rule Set Website to ensure that it is installed properly using the Extended Install page.)

🧱 Installation Process
To use our custom version of the ModSecurity WAF you need to download the custom-rules.conf file and the common-passwords.txt file. Once those are downloaded the next step is to place them in the same folders as shown in our GitHub repository. The custom-rules.conf file goes into the rules folder of the OWASP Core Rule Set you have set up. The common-passwords.txt file goes in the parent directory of the rules folder. Once that is done the next step is to use the commands chmod and chown on both of those files to give is the sufficient permissions for it to work, you will need sudo privileges to complete the commands.

The commands will look like this:
**sudo chown www-data:www-data custom-rules.conf
sudo chown www-data:www-data common-passwords.txt
sudo chmod 644 custom-rules.conf
sudo chmod 644 common-passwords.txt**

Once you input those commands you should restart your web server (Apache or Nginx) and then make sure ModSecurity is running. Once done ou can run a test on yourself to make sure that it is inputting the correct information to the log files that were set up when installing OWASP Core Rule Set. ie. the audit log and the debug log.

# VPS Gegevens Overzicht - Hetzner Server

> **📋 Essentiële server informatie voor hosting van websites voor derden**
>
> **⚠️ VERTROUWELIJK - Niet delen met derden klanten!**

---

## 🔐 SSH Toegang

### Inloggegevens
```
Host: 188.245.159.115
User: root
Port: 22
Auth Type: SSH Key (passwordless)
SSH Key Path: C:\Users\henkv\.ssh\id_ed25519
```

### Inloggen
```bash
# Direct SSH
ssh root@188.245.159.115

# Of met config alias (als geconfigureerd)
ssh hetzner
```

### SSH Key Locatie (Windows)
```
Private Key: C:\Users\henkv\.ssh\id_ed25519
Public Key:  C:\Users\henkv\.ssh\id_ed25519.pub
```

---

## 🖥️ Server Specificaties

### Hardware & Hosting
```
Provider:    Hetzner Cloud
Plan:        CX22 VPS
RAM:         4 GB
CPU:         2 vCPU (AMD EPYC)
Storage:     40 GB NVMe SSD
OS:          Ubuntu 22.04.5 LTS
Kernel:      5.15.0-151-generic x86_64
```

### Netwerk
```
IPv4:        188.245.159.115
IPv6:        2a01:4f8:1c1a:457f::1
Hostname:    herdenkingsportaal-prod
Locatie:     Falkenstein, Duitsland
```

### Huidige Status (11 nov 2025)
```
Disk Usage:  13.6% van 37.23GB (gezond)
Memory:      ~32% gebruikt (~1.3GB van 4GB)
Load Avg:    0.02-0.22 (zeer laag, gezond)
Uptime:      Zeer hoog (stabiel)
```

---

## 🌐 Web Server Stack

### Installed Software
```
Webserver:   Nginx
PHP:         8.1 + 8.2 (PHP-FPM)
Database:    MySQL 8.x
SSL:         Certbot (Let's Encrypt)
Git:         Installed
Composer:    Installed
Node/NPM:    Installed
```

### Service Commands
```bash
# Nginx
systemctl status nginx
systemctl restart nginx
systemctl reload nginx

# PHP-FPM
systemctl status php8.2-fpm
systemctl restart php8.2-fpm

# MySQL
systemctl status mysql
mysql -u root -p
```

---

## 📂 Directory Structuur

### Web Root
```
Base:  /var/www/

Huidige sites:
/var/www/production/    # Herdenkingsportaal (LIVE)
/var/www/staging/       # Herdenkingsportaal (TEST)
/var/www/havunadmin/    # HavunAdmin site
/var/www/vpdupdate/     # VPD Update site
/var/www/intro/         # Intro static site
```

### Voor Nieuwe Sites
```
Locatie: /var/www/[sitename]/
Owner:   www-data:www-data
Perms:   755 (directories), 644 (files)
```

---

## 🔧 Nginx Configuratie

### Config Files
```
Main Config:      /etc/nginx/nginx.conf
Sites Available:  /etc/nginx/sites-available/
Sites Enabled:    /etc/nginx/sites-enabled/
Logs:             /var/log/nginx/
```

### Server Block Template (Laravel)
```nginx
server {
    listen 80;
    server_name example.com www.example.com;
    root /var/www/example/public;
    index index.php index.html;

    location / {
        try_files $uri $uri/ /index.php?$query_string;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }

    error_log /var/log/nginx/example-error.log;
    access_log /var/log/nginx/example-access.log;
}
```

### Commands
```bash
# Enable site (symlink)
ln -s /etc/nginx/sites-available/sitename.conf /etc/nginx/sites-enabled/

# Disable site
rm /etc/nginx/sites-enabled/sitename.conf

# Test config
nginx -t

# Reload (no downtime)
systemctl reload nginx

# List enabled sites
ls -la /etc/nginx/sites-enabled/
```

---

## 🔒 SSL Certificaten

### Certbot (Let's Encrypt)
```bash
# Install SSL voor nieuwe site
certbot --nginx -d example.com -d www.example.com

# Test renewal
certbot renew --dry-run

# Force renewal
certbot renew --force-renewal

# List certificates
certbot certificates
```

### Bestaande Certificaten
```
herdenkingsportaal.nl (production)
staging.herdenkingsportaal.nl
havunadmin (production + staging)
vpdupdate
```

**Auto-renewal:** Geconfigureerd via systemd timer

---

## 🗄️ MySQL Database

### Root Access
```bash
# Login als root
mysql -u root -p
# Wachtwoord: [Opgeslagen in /root/.my.cnf of server notes]
```

### Database Aanmaken voor Nieuwe Site
```sql
CREATE DATABASE sitename_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'sitename_user'@'localhost' IDENTIFIED BY 'STERK_WACHTWOORD';
GRANT ALL PRIVILEGES ON sitename_db.* TO 'sitename_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

### Bestaande Databases
```
herdenkingsportaal (production)
herdenkingsportaal_staging
havunadmin (production + staging)
vpdupdate
```

---

## 🔥 Firewall (UFW)

### Status
```bash
ufw status verbose
```

### Allowed Ports
```
22   (SSH)
80   (HTTP)
443  (HTTPS)
```

**⚠️ Wijzig firewall ALLEEN als je weet wat je doet!**

---

## 📊 Monitoring & Logs

### System Logs
```bash
# Nginx errors
tail -f /var/log/nginx/[sitename]-error.log

# Nginx access
tail -f /var/log/nginx/[sitename]-access.log

# System log
tail -f /var/log/syslog

# Auth log (SSH logins)
tail -f /var/log/auth.log
```

### Resource Usage
```bash
# Disk space
df -h

# Memory usage
free -h

# CPU & processes
top
htop  # (indien geïnstalleerd)

# Server uptime & load
uptime

# Network connections
netstat -tulnp
```

---

## 🚀 File Transfer Methoden

### 1. SCP (Command Line)
```bash
# Upload file
scp C:/local/file.txt root@188.245.159.115:/var/www/sitename/

# Upload directory
scp -r C:/local/folder/* root@188.245.159.115:/var/www/sitename/

# Download file
scp root@188.245.159.115:/var/www/sitename/file.txt C:/local/
```

### 2. SFTP (FileZilla, WinSCP)
```
Protocol:  SFTP
Host:      188.245.159.115
Port:      22
User:      root
Auth:      SSH Key (C:\Users\henkv\.ssh\id_ed25519)
```

### 3. Git (Aanbevolen voor Code)
```bash
cd /var/www/sitename
git clone https://github.com/user/repo.git .
git pull origin main
```

---

## 🔄 Quick Commands Cheatsheet

```bash
# === SYSTEM ===
ssh root@188.245.159.115        # Login
exit                            # Logout
sudo su                         # Wissel naar root (al root)
reboot                          # Reboot server (VOORZICHTIG!)
shutdown -h now                 # Shutdown server

# === NGINX ===
systemctl status nginx          # Status check
systemctl restart nginx         # Restart (downtime!)
systemctl reload nginx          # Reload config (geen downtime)
nginx -t                        # Test configuratie
ln -s /etc/nginx/sites-available/site.conf /etc/nginx/sites-enabled/  # Enable site
rm /etc/nginx/sites-enabled/site.conf  # Disable site

# === PHP ===
systemctl status php8.2-fpm    # Status
systemctl restart php8.2-fpm   # Restart PHP
php -v                         # PHP versie

# === MYSQL ===
systemctl status mysql         # Status
mysql -u root -p              # Login MySQL
systemctl restart mysql       # Restart MySQL

# === FILES ===
ls -la /var/www/              # List sites
chown -R www-data:www-data /var/www/site/  # Fix ownership
chmod -R 755 /var/www/site/   # Fix permissions

# === LOGS ===
tail -f /var/log/nginx/error.log         # Nginx errors
tail -f /var/log/nginx/access.log        # Nginx access
journalctl -u nginx -f                   # Systemd logs (live)

# === RESOURCES ===
df -h                         # Disk space
free -h                       # Memory
top                           # Processes (q om te stoppen)
uptime                        # Uptime & load average
```

---

## 🆘 Emergency Contacts & Resources

### Hetzner Support
```
Cloud Console: https://console.hetzner.cloud/
Support:       https://docs.hetzner.com/
Emergency:     Via Hetzner Cloud Console
```

### Server Owner
```
Email: havun22@gmail.com
```

### Important Docs
```
Nginx Docs:    https://nginx.org/en/docs/
Certbot Docs:  https://certbot.eff.org/
Laravel Docs:  https://laravel.com/docs
```

---

## ⚠️ VEILIGHEIDSREGELS

### NOOIT DOEN zonder backup:
- ❌ `rm -rf /var/www/*` (verwijdert ALLE sites!)
- ❌ `DROP DATABASE` zonder backup
- ❌ Firewall wijzigen (kan je buitensluiten!)
- ❌ Nginx config verwijderen zonder backup

### ALTIJD DOEN:
- ✅ Backup maken VOOR grote wijzigingen
- ✅ `nginx -t` NA config wijzigingen
- ✅ Logs checken NA deployment
- ✅ SSL certificaten op tijd vernieuwen
- ✅ Security updates installeren

### BACKUP LOCATIES:
```
Manual Backups:     /root/backups/
Database Dumps:     /root/db_backups/
Hetzner Snapshots:  Via Cloud Console
```

---

## 📝 Server Maintenance Schema

### Dagelijks
- Check disk space (`df -h`)
- Check logs voor errors

### Wekelijks
- Security updates: `apt update && apt upgrade`
- Check SSL certificate expiry
- Backup databases

### Maandelijks
- Review Nginx logs
- Clean old log files
- Check resource usage trends
- Review firewall rules

---

**📅 Document Versie:** 2.0
**🗓️ Laatst Bijgewerkt:** 26 november 2025
**👤 Beheerder:** Henk (havun22@gmail.com)
**🔒 Classificatie:** VERTROUWELIJK

---

## 🎯 Voor Gebruik in Andere Claude Chat

**Kopieer en plak dit document** in je andere Claude sessie met de instructie:

> "Ik wil een nieuwe website hosten op deze VPS. Gebruik de bovenstaande gegevens om me te helpen met het opzetten van [sitenaam]. De site is een [Laravel/WordPress/Static HTML] website."

Claude kan dan direct aan de slag met de correcte server informatie! 🚀

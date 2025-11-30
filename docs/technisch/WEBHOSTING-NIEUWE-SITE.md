# Webhosting Nieuwe Site op Hetzner VPS

> **📋 Complete instructie voor het hosten van een nieuwe website op dezelfde server als Herdenkingsportaal**

---

## 🖥️ Server Informatie

### Toegang
- **SSH Host:** 188.245.159.115
- **SSH User:** root
- **SSH Key:** `C:\Users\henkv\.ssh\id_ed25519`
- **Inloggen:**
  ```bash
  ssh root@188.245.159.115
  # OF met config alias:
  ssh hetzner
  ```

### Server Specificaties
- **Provider:** Hetzner Cloud CX22
- **OS:** Ubuntu 22.04.5 LTS
- **RAM:** 4 GB
- **Storage:** 40 GB NVMe SSD
- **CPU:** 2 vCPU AMD EPYC
- **Webserver:** Nginx

### Huidige Sites op Server
De server host momenteel:
1. **herdenkingsportaal.nl** (production + staging)
2. **havunadmin** (production + staging)
3. **vpdupdate** (production)

---

## 📂 Directory Structuur

Alle websites staan in `/var/www/`:

```
/var/www/
├── production/          # Herdenkingsportaal production
├── staging/             # Herdenkingsportaal staging
├── havunadmin/          # HavunAdmin site
├── vpdupdate/           # VPD Update site
└── html/                # Nginx default
```

**Nieuwe sites komen in:** `/var/www/jouwesite/`

---

## 🚀 Stap-voor-Stap: Nieuwe Site Toevoegen

### STAP 1: Inloggen op Server

```bash
ssh root@188.245.159.115
```

### STAP 2: Maak Directory voor Nieuwe Site

```bash
# Maak directory
mkdir -p /var/www/jouwesite

# Set correcte ownership (www-data is Nginx user)
chown -R www-data:www-data /var/www/jouwesite

# Set correcte permissions
chmod 755 /var/www/jouwesite
```

### STAP 3: Upload Website Files

**Optie A: Via Git (aanbevolen voor Laravel/code projecten)**
```bash
cd /var/www/jouwesite
git clone https://github.com/jouw-repo/jouw-project.git .
```

**Optie B: Via SCP (voor static sites of zip files)**
```bash
# Vanaf je lokale machine:
scp -r C:/pad/naar/website/* root@188.245.159.115:/var/www/jouwesite/
```

**Optie C: Via FTP/SFTP (FileZilla, WinSCP)**
- Host: `188.245.159.115`
- Protocol: SFTP
- Port: 22
- User: root
- Auth: SSH Key (`C:\Users\henkv\.ssh\id_ed25519`)

### STAP 4: Nginx Server Block Configuratie

Maak een Nginx config file:

```bash
nano /etc/nginx/sites-available/jouwesite.conf
```

**Voor een Static HTML/PHP site:**
```nginx
server {
    listen 80;
    server_name jouwesite.nl www.jouwesite.nl;
    root /var/www/jouwesite;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ =404;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }

    error_log /var/log/nginx/jouwesite-error.log;
    access_log /var/log/nginx/jouwesite-access.log;
}
```

**Voor een Laravel site:**
```nginx
server {
    listen 80;
    server_name jouwesite.nl www.jouwesite.nl;
    root /var/www/jouwesite/public;
    index index.php index.html index.htm;

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

    error_log /var/log/nginx/jouwesite-error.log;
    access_log /var/log/nginx/jouwesite-access.log;
}
```

**Voor een WordPress site:**
```nginx
server {
    listen 80;
    server_name jouwesite.nl www.jouwesite.nl;
    root /var/www/jouwesite;
    index index.php index.html index.htm;

    location / {
        try_files $uri $uri/ /index.php?$args;
    }

    location ~ \.php$ {
        fastcgi_pass unix:/var/run/php/php8.2-fpm.sock;
        fastcgi_param SCRIPT_FILENAME $realpath_root$fastcgi_script_name;
        include fastcgi_params;
    }

    location ~ /\.ht {
        deny all;
    }

    # WordPress specifiek: uploads limiet
    client_max_body_size 64M;

    error_log /var/log/nginx/jouwesite-error.log;
    access_log /var/log/nginx/jouwesite-access.log;
}
```

**Opslaan:** `Ctrl+O` → `Enter` → `Ctrl+X`

### STAP 5: Enable Site & Reload Nginx

```bash
# Enable de nieuwe site (symlink maken)
ln -s /etc/nginx/sites-available/jouwesite.conf /etc/nginx/sites-enabled/

# Test Nginx configuratie (BELANGRIJK!)
nginx -t

# Als test OK is, reload Nginx
systemctl reload nginx

# Check Nginx status
systemctl status nginx
```

### STAP 6: DNS Configuratie

**Bij je domain registrar (bijvoorbeeld TransIP, Cloudflare, etc.):**

Voeg deze DNS records toe:
```
Type    Name    Value               TTL
A       @       188.245.159.115     3600
A       www     188.245.159.115     3600
```

**DNS propagatie duurt 15 minuten - 48 uur.**

Test DNS met:
```bash
nslookup jouwesite.nl
# Moet 188.245.159.115 tonen
```

### STAP 7: SSL Certificaat (HTTPS) - Verplicht!

**Wacht tot DNS werkt**, dan:

```bash
# Vraag gratis SSL certificaat aan
certbot --nginx -d jouwesite.nl -d www.jouwesite.nl

# Volg de prompts:
# - Email: havun22@gmail.com
# - Terms: Yes
# - Redirect HTTP to HTTPS: Yes (aanbevolen)
```

Certbot past automatisch de Nginx config aan met SSL settings.

### STAP 8: Laravel Specifieke Setup (indien van toepassing)

```bash
cd /var/www/jouwesite

# Install Composer dependencies
composer install --no-dev --optimize-autoloader

# Setup .env file
cp .env.example .env
nano .env  # Configureer database, etc.

# Generate app key
php artisan key:generate

# Run migrations
php artisan migrate --force

# Create storage symlink
php artisan storage:link

# Set permissions
chown -R www-data:www-data storage bootstrap/cache
chmod -R 775 storage bootstrap/cache

# Clear caches
php artisan config:cache
php artisan route:cache
php artisan view:cache
```

---

## 🗄️ Database Setup (voor Laravel/PHP/WordPress sites)

### MySQL Database Aanmaken

```bash
# Login MySQL als root
mysql -u root -p

# Maak database + user
CREATE DATABASE jouwesite_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'jouwesite_user'@'localhost' IDENTIFIED BY 'STERK_WACHTWOORD_HIER';
GRANT ALL PRIVILEGES ON jouwesite_db.* TO 'jouwesite_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;
```

Update `.env` (Laravel) of `wp-config.php` (WordPress):
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=jouwesite_db
DB_USERNAME=jouwesite_user
DB_PASSWORD=STERK_WACHTWOORD_HIER
```

---

## 🔧 Beheer & Onderhoud

### Logs Bekijken

```bash
# Nginx error log
tail -f /var/log/nginx/jouwesite-error.log

# Nginx access log
tail -f /var/log/nginx/jouwesite-access.log

# Laravel logs (indien Laravel)
tail -f /var/www/jouwesite/storage/logs/laravel.log

# WordPress debug log (indien WP_DEBUG_LOG aan)
tail -f /var/www/jouwesite/wp-content/debug.log
```

### Site Updaten

**Voor Laravel sites:**
```bash
cd /var/www/jouwesite
git pull origin main
composer install --no-dev --optimize-autoloader
php artisan migrate --force
php artisan config:clear
php artisan cache:clear
php artisan view:clear
systemctl reload nginx
```

**Voor WordPress sites:**
```bash
# Updates via WordPress admin (wp-admin)
# Of via WP-CLI:
cd /var/www/jouwesite
wp core update
wp plugin update --all
wp theme update --all
```

**Voor static sites:**
```bash
# Upload nieuwe bestanden via SCP/SFTP
# Geen verdere stappen nodig
```

### Disk Space Check

```bash
df -h
# Kijk naar /dev/sda1 usage (moet onder 80% blijven)
```

### Performance Monitoring

```bash
# Server load
uptime

# Memory usage
free -h

# Top processes
top
# Press 'q' om te stoppen
```

---

## 🔐 Security Checklist

- [ ] SSL certificaat geïnstalleerd (HTTPS)
- [ ] Firewall (UFW) configured:
  ```bash
  ufw status  # Check huidige rules
  # Standaard: SSH (22), HTTP (80), HTTPS (443) toegestaan
  ```
- [ ] Sterke database wachtwoorden
- [ ] `.env` files NIET in git (`.gitignore`)
- [ ] Directory listing uitgeschakeld (standaard in Nginx)
- [ ] Nginx versie info verbergen

---

## 📋 Beschikbare PHP Versies

De server heeft:
- **PHP 8.1** - `/var/run/php/php8.1-fpm.sock`
- **PHP 8.2** - `/var/run/php/php8.2-fpm.sock` (aanbevolen)

**Aanbevolen:** PHP 8.2 voor nieuwe sites (modernere versie)

---

## 🆘 Troubleshooting

### Site toont "403 Forbidden"
```bash
# Check permissions
ls -la /var/www/jouwesite/
# Moet www-data:www-data zijn

# Fix permissions
chown -R www-data:www-data /var/www/jouwesite
chmod 755 /var/www/jouwesite
```

### Site toont "502 Bad Gateway"
```bash
# PHP-FPM draait niet
systemctl status php8.2-fpm
systemctl restart php8.2-fpm

# Check socket path in nginx config
# Moet matchen met PHP-FPM socket
```

### Site toont "500 Internal Server Error"
```bash
# Check Nginx error log
tail -50 /var/log/nginx/jouwesite-error.log

# Check Laravel log (indien Laravel)
tail -50 /var/www/jouwesite/storage/logs/laravel.log
```

### DNS werkt niet
```bash
# Check DNS propagatie
nslookup jouwesite.nl
dig jouwesite.nl

# Kan 24-48 uur duren!
```

### SSL certificaat vernieuwt niet automatisch
```bash
# Test renewal
certbot renew --dry-run

# Force renewal (als certificaat < 30 dagen geldig)
certbot renew --force-renewal
```

---

## 📞 Contacts & Resources

- **Server Login:** `ssh root@188.245.159.115`
- **Hetzner Cloud Panel:** https://console.hetzner.cloud/
- **Certbot Docs:** https://certbot.eff.org/
- **Nginx Docs:** https://nginx.org/en/docs/

---

## 🔄 Quick Reference Commands

```bash
# Inloggen
ssh root@188.245.159.115

# Nginx herstarten
systemctl restart nginx

# Nginx reload (zachter, geen downtime)
systemctl reload nginx

# Nginx status
systemctl status nginx

# Nginx config test
nginx -t

# Enable site
ln -s /etc/nginx/sites-available/jouwesite.conf /etc/nginx/sites-enabled/

# Disable site
rm /etc/nginx/sites-enabled/jouwesite.conf

# List enabled sites
ls -la /etc/nginx/sites-enabled/

# Check disk space
df -h

# Check memory
free -h

# Check running processes
top
```

---

**📅 Document Versie:** 2.0
**🗓️ Laatst Bijgewerkt:** 26 november 2025
**✍️ Auteur:** Henk - Havun Web Services

**✅ Server Status:** Operationeel met Nginx

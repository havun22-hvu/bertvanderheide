# Complete Website Migratie Methoden

> **🎯 Betrouwbare manieren om een klant's website volledig te downloaden en migreren**

---

## 📋 Overzicht: Welke Methode Wanneer?

```
┌─────────────────────────────────────────────────────────────┐
│ TYPE SITE        │ TOEGANG NODIG    │ BESTE METHODE       │
├──────────────────┼──────────────────┼─────────────────────┤
│ WordPress        │ Admin login      │ #1: Duplicator      │
│ WordPress        │ FTP/cPanel       │ #2: Handmatig       │
│ WordPress        │ Geen toegang     │ #5: HTTrack (last)  │
│ Laravel/PHP      │ FTP/SSH          │ #2: Handmatig       │
│ Static HTML      │ FTP              │ #2: FTP Download    │
│ Static HTML      │ Geen toegang     │ #5: HTTrack/wget    │
│ OnbekendeUnknown │ Eerst checken    │ #0: Site Analyse    │
└─────────────────────────────────────────────────────────────┘
```

---

## #0: Eerst Analyseren - Wat Voor Site Is Het?

**STAP 0 - Voordat je iets download:**

### A. Check Site Type (Vanaf Browser)
```
1. Open developer tools (F12 in Chrome)
2. Ga naar Network tab
3. Refresh de pagina
4. Kijk naar:
   - HTML response headers
   - Files die laden (.php? .aspx? static .html?)
   - URL structuur (/wp-admin/, /administrator/, etc)
```

### B. WordPress Detectie
**Makkelijkste Check:**
```
Ga naar: https://bertvanderheide.nl/wp-admin/
Resultaat:
├─ Login scherm? → WordPress! ✅
├─ 404 niet gevonden? → Geen WordPress
└─ Redirect naar andere login? → Ander CMS
```

**Of check source code:**
```html
<!-- Zoek naar in HTML: -->
<meta name="generator" content="WordPress 6.x" />
/wp-content/
/wp-includes/
wp-json (in browser URL bar)
```

### C. Andere CMS Detectie
```
Joomla:     /administrator/
Drupal:     /user/login
Wix:        .wixsite.com in URL
Squarespace: Specifieke JS libraries
```

### D. Online Tools
```
https://builtwith.com/bertvanderheide.nl
https://www.wappalyzer.com/

Geeft terug:
- CMS (WordPress, Joomla, etc)
- Server (Apache, Nginx)
- Hosting provider
- JavaScript libraries
```

---

## #1: WordPress - Duplicator Plugin (BESTE Methode!)

**✅ Voordelen:** Complete site + database in 1 ZIP
**❌ Nadelen:** Vereist WordPress admin toegang
**⏱️ Tijd:** 15-30 minuten

### Stap-voor-Stap

**1. Login WordPress Admin**
```
https://bertvanderheide.nl/wp-admin/
Username: [vraag aan klant]
Password: [vraag aan klant]
```

**2. Installeer Duplicator Plugin**
```
WordPress Admin → Plugins → Add New
Zoek: "Duplicator"
Installeer: "Duplicator - WordPress Migration Plugin"
Activate plugin
```

**3. Maak Backup Package**
```
Duplicator → Create New

Settings:
├─ Name: bertvanderheide-backup-2025-11-12
├─ Storage: Default (local download)
├─ Archive: Include everything
└─ Installer: Yes (automatisch mee)

Klik: "Next" → "Build"
Wacht: 2-10 minuten (afhankelijk van site grootte)
```

**4. Download 2 Files**
```
Je krijgt 2 files:
1. installer.php           (klein bestand, ~1MB)
2. [naam]_[hash].zip      (grote ZIP met alles)

Download BEIDE naar lokale machine!
```

**5. Check Wat Je Hebt**
```
De ZIP bevat:
├─ /wp-content/           (themes, plugins, uploads)
├─ /wp-includes/          (WordPress core)
├─ wp-config.php          (database settings - wijzigen!)
├─ database.sql           (complete database dump!)
└─ Alle andere files

= COMPLETE SITE! 🎉
```

**6. Upload Naar Nieuwe Server**
```bash
# Via SCP (vanaf lokale machine)
scp installer.php root@188.245.159.115:/var/www/bertvanderheide.nl/
scp [naam].zip root@188.245.159.115:/var/www/bertvanderheide.nl/

# Of via SFTP (FileZilla):
# Host: 188.245.159.115
# Upload beide files naar /var/www/bertvanderheide.nl/
```

**7. Run Installer (Via Browser)**
```
1. Setup Apache VirtualHost (zie andere docs)
2. DNS instellen (A-record naar 188.245.159.115)
3. Ga naar: https://bertvanderheide.nl/installer.php

Installer wizard:
├─ Step 1: Pre-flight check
├─ Step 2: Database settings (nieuwe database!)
│   DB Host: 127.0.0.1
│   DB Name: bert_db (nieuw aanmaken!)
│   DB User: bert_user
│   DB Pass: [sterk wachtwoord]
├─ Step 3: Install/Extract
└─ Step 4: Update URLs, test site

Done! ✅
```

**8. Cleanup & Security**
```bash
# Verwijder installer files (BELANGRIJK!)
ssh root@188.245.159.115
cd /var/www/bertvanderheide.nl/
rm installer.php
rm [naam].zip
rm installer-backup.php
rm installer-log.txt

# Update WordPress admin password (niet vertrouwen op oude)
# Via phpMyAdmin of wp-cli
```

---

## #2: Handmatig - FTP/cPanel/SSH Toegang (Universeel)

**✅ Voordelen:** Werkt voor ALLE site types (WP, Laravel, static)
**❌ Nadelen:** Database apart downloaden
**⏱️ Tijd:** 30-60 minuten

### Stap-voor-Stap

**1. Vraag Toegang aan Klant**
```
Vraag klant om:
├─ FTP/SFTP credentials
│   Host: ftp.huidigehoster.nl
│   Username: gebruiker123
│   Password: wachtwoord
│   Port: 21 (FTP) of 22 (SFTP)
│
├─ cPanel login (als beschikbaar)
│   URL: https://huidigehoster.nl:2083
│   Username: [klant]
│   Password: [klant]
│
└─ SSH toegang (beste optie!)
    Host: ssh.huidigehoster.nl
    Username: klant
    Port: 22
```

**2A. Download via SFTP (FileZilla)**
```
FileZilla installeren (gratis):
https://filezilla-project.org/

Connect:
├─ Host: ftp.huidigehoster.nl (of IP)
├─ Username: [van klant]
├─ Password: [van klant]
├─ Port: 22 (SFTP) of 21 (FTP)
└─ Connect

Download:
├─ Rechterkant: Server files
├─ Linkerkant: Lokale folder (bijv. C:\Temp\bert-site\)
├─ Selecteer: public_html/ (of httpdocs/ of www/)
├─ Rechtermuisklik → Download
└─ Wacht: 5-60 minuten (afhankelijk van grootte)
```

**2B. Download via SCP (Command Line - Sneller!)**
```bash
# Vanaf je Windows machine (in PowerShell of Git Bash)
scp -r klant@huidigehoster.nl:/home/klant/public_html/* C:/Temp/bert-site/

# Of met rsync (als beschikbaar, sneller + resume!)
rsync -avz --progress klant@huidigehoster.nl:/home/klant/public_html/ C:/Temp/bert-site/
```

**2C. Download via cPanel File Manager**
```
cPanel → File Manager → public_html/
├─ Select All
├─ Compress → ZIP
├─ Wait...
├─ Download ZIP file
└─ Extract lokaal
```

**3. Download Database**

**Optie A: cPanel phpMyAdmin**
```
cPanel → phpMyAdmin
├─ Selecteer database (vaak naam van site)
├─ Tab: "Export"
├─ Method: Quick
├─ Format: SQL
├─ Click: "Export"
└─ Download: [database].sql (bijv. bert_db.sql)
```

**Optie B: SSH mysqldump**
```bash
# SSH naar oude server
ssh klant@huidigehoster.nl

# Dump database
mysqldump -u db_user -p database_name > backup.sql

# Download vanaf je lokale machine
scp klant@huidigehoster.nl:backup.sql C:/Temp/bert-site/
```

**Optie C: WordPress Plugin (als WP)**
```
WP Admin → Plugins → Add New
Install: "WP-DB-Backup" of "BackWPup"
Create manual backup
Download .sql file
```

**4. Check Wat Je Hebt**
```
C:\Temp\bert-site\
├─ index.php (of index.html)
├─ /wp-content/ (als WordPress)
├─ /images/
├─ /css/
├─ /js/
├─ .htaccess
└─ backup.sql (database!)

✅ Compleet? Ga naar stap 5
❌ Incomplete? Check FTP/cPanel opnieuw
```

**5. Upload Naar Nieuwe Server**
```bash
# Via SCP (meerdere files? Eerst ZIP maken!)
# Vanaf lokale machine:
scp -r C:/Temp/bert-site/* root@188.245.159.115:/var/www/bertvanderheide.nl/

# Of ZIP maken en uploaden (sneller!)
# Windows: Rechtermuisklik → "Compress to ZIP"
scp C:/Temp/bert-site.zip root@188.245.159.115:/tmp/
ssh root@188.245.159.115
cd /var/www/bertvanderheide.nl/
unzip /tmp/bert-site.zip
chown -R www-data:www-data /var/www/bertvanderheide.nl/
```

**6. Importeer Database**
```bash
# SSH naar nieuwe server
ssh root@188.245.159.115

# Maak nieuwe database
mysql -u root -p
CREATE DATABASE bert_db CHARACTER SET utf8mb4 COLLATE utf8mb4_unicode_ci;
CREATE USER 'bert_user'@'localhost' IDENTIFIED BY 'SterkWachtwoord123!';
GRANT ALL ON bert_db.* TO 'bert_user'@'localhost';
FLUSH PRIVILEGES;
EXIT;

# Importeer oude database
mysql -u bert_user -p bert_db < /var/www/bertvanderheide.nl/backup.sql

# Check import
mysql -u bert_user -p bert_db
SHOW TABLES;
EXIT;
```

**7. Update Config Files**

**WordPress: wp-config.php**
```php
// /var/www/bertvanderheide.nl/wp-config.php

define( 'DB_NAME', 'bert_db' );              // ← Nieuwe database naam
define( 'DB_USER', 'bert_user' );            // ← Nieuwe user
define( 'DB_PASSWORD', 'SterkWachtwoord123!' ); // ← Nieuw wachtwoord
define( 'DB_HOST', 'localhost' );            // ← Blijft localhost

// Update site URL (als domein hetzelfde blijft, niet nodig)
```

**Laravel: .env**
```env
DB_CONNECTION=mysql
DB_HOST=127.0.0.1
DB_PORT=3306
DB_DATABASE=bert_db
DB_USERNAME=bert_user
DB_PASSWORD=SterkWachtwoord123!

APP_URL=https://bertvanderheide.nl
```

**8. WordPress URL Fix (Als Nodig)**
```sql
# Als de site nu naar oude URL redirect:
mysql -u bert_user -p bert_db

UPDATE wp_options SET option_value='https://bertvanderheide.nl'
WHERE option_name='siteurl';

UPDATE wp_options SET option_value='https://bertvanderheide.nl'
WHERE option_name='home';

EXIT;
```

---

## #3: SSH Rsync (Als Je Toegang Hebt Tot Beide Servers)

**✅ Voordelen:** Snelste, meest betrouwbare methode
**❌ Nadelen:** Vereist SSH toegang beide servers
**⏱️ Tijd:** 10-30 minuten

```bash
# Vanaf NIEUWE server (jouw Hetzner)
ssh root@188.245.159.115

# Rsync vanaf oude server naar nieuwe
rsync -avz --progress \
  klant@oude-server.nl:/home/klant/public_html/ \
  /var/www/bertvanderheide.nl/

# Database rsync
rsync -avz --progress \
  klant@oude-server.nl:/tmp/database-backup.sql \
  /var/www/bertvanderheide.nl/

# Voordelen:
# - Resume bij interrupt
# - Alleen gewijzigde files
# - Permissions behouden
# - Symbolische links correct
```

---

## #4: Hosting Provider Backup (Vraag aan Klant)

**✅ Voordelen:** Complete backup, door provider gemaakt
**❌ Nadelen:** Klant moet vragen bij oude host
**⏱️ Tijd:** 1 dag (wachttijd) + 30 min download

```
Mail aan oude hosting provider:
───────────────────────────────────────
Onderwerp: Volledige backup aanvragen voor [domein]

Beste [provider],

Ik wil mijn website [bertvanderheide.nl] migreren
naar een andere host. Kan ik een volledige backup
ontvangen met:
1. Alle website bestanden (FTP root)
2. Database dump (MySQL)
3. Email accounts (optioneel)

Graag als downloadlink of ZIP file.

Met vriendelijke groet,
[Klant naam]
───────────────────────────────────────

Vaak krijg je binnen 24-48 uur:
├─ backup.tar.gz (alle files)
├─ database.sql.gz (database)
└─ Instructies
```

---

## #5: HTTrack/wget (LAATSTE OPTIE - Geen Toegang)

**✅ Voordelen:** Werkt zonder toegang
**❌ Nadelen:** Mist backend, database, dynamische content
**⏱️ Tijd:** 1-4 uur
**⚠️ Gebruik alleen als je echt geen toegang kunt krijgen!**

### HTTrack (Windows GUI)

**Installatie:**
```
Download: https://www.httrack.com/
Install: HTTrack Website Copier
```

**Gebruik:**
```
1. Open HTTrack
2. Project Name: bert-site
3. Base Path: C:\Temp\httrack\
4. Web Addresses: https://bertvanderheide.nl
5. Options:
   ├─ Scan Rules: +*bertvanderheide.nl/* (alleen deze site)
   ├─ Limits: No external links
   ├─ Flow Control: 4 connections, 25% speed (niet te agressief)
   └─ Browser ID: Mozilla/5.0 (normaal browser)
6. Start!
7. Wacht: 30-120 minuten

Result:
C:\Temp\httrack\bert-site\
└─ Static HTML copy (GEEN database, GEEN PHP backend)
```

### wget (Command Line)

```bash
wget --mirror \
     --convert-links \
     --adjust-extension \
     --page-requisites \
     --no-parent \
     --wait=1 \
     --limit-rate=200k \
     --user-agent="Mozilla/5.0" \
     https://bertvanderheide.nl

# Flags uitleg:
# --mirror: Recursief downloaden
# --convert-links: Links naar lokale files
# --adjust-extension: .html toevoegen
# --page-requisites: CSS/JS/images
# --no-parent: Niet naar parent directories
# --wait=1: 1 sec tussen requests (beleefd)
# --limit-rate: Max 200KB/s (niet te agressief)
```

**⚠️ Beperkingen HTTrack/wget:**
```
✅ Downloaded:
├─ Static HTML
├─ CSS files
├─ JavaScript
├─ Images
└─ Public downloads

❌ NIET Downloaded:
├─ WordPress admin area
├─ Database inhoud
├─ PHP backend logic
├─ .htaccess (vaak)
├─ Login-protected pages
├─ Dynamisch gegenereerde content
└─ Forms (werken niet meer!)

= Alleen bruikbaar voor simpele static conversie!
```

---

## #6: Hybride Methode - Best of Both

**Voor Maximale Zekerheid:**

```
1. HTTrack/wget (frontend copy) → Voor fallback
2. FTP download (echte files)   → Voor deployment
3. Database dump (phpMyAdmin)   → Voor data
4. Screenshots maken            → Voor design reference

= Je hebt nu:
  ├─ Static backup (emergency)
  ├─ Echte files (deployment)
  ├─ Database (functionaliteit)
  └─ Visual reference (design check)
```

---

## 📋 Checklist: Complete Site Download

**✅ Voor Je Begint:**
```
□ Site type bepalen (WordPress/Laravel/Static)
□ Toegang aanvragen bij klant (FTP/cPanel/Admin)
□ Disk space checken (lokaal & server)
□ Backup strategie kiezen (methode #1-5)
```

**✅ Tijdens Download:**
```
□ Alle files gedownload (check file count!)
□ Database gedownload (.sql file)
□ .htaccess file mee (vaak verborgen!)
□ wp-config.php of .env file (config!)
□ /uploads/ folder (media files!)
□ Verify download (geen 0 byte files)
```

**✅ Na Download, Voor Upload:**
```
□ ZIP maken van alle files (makkelijker uploaden)
□ Database .sql backup apart houden
□ Wachtwoorden noteren (oude database credentials)
□ Screenshot maken oude site (design reference)
```

**✅ Na Upload op Nieuwe Server:**
```
□ Files ownership: www-data:www-data
□ Permissions: 755 directories, 644 files
□ Database geïmporteerd en getest
□ Config files aangepast (wp-config/env)
□ URLs updated (WordPress wp_options)
□ SSL certificaat (Certbot)
□ Test alle pagina's!
□ Test contactformulier!
```

---

## 🛠️ Tools Installeren (Windows)

### Aanbevolen Software:
```
1. FileZilla (FTP/SFTP)
   https://filezilla-project.org/
   → Voor file downloads

2. HeidiSQL (MySQL GUI)
   https://www.heidisql.com/
   → Voor database management

3. 7-Zip (Compression)
   https://www.7-zip.org/
   → Voor ZIP maken/uitpakken

4. HTTrack (Website Copier)
   https://www.httrack.com/
   → Last resort website mirroring

5. Git for Windows (rsync, bash)
   https://git-scm.com/
   → Command line tools
```

---

## 🚨 Common Issues & Fixes

### Issue #1: HTTrack Incomplete Download
```
Symptoom: HTTrack zegt "done" maar site is incomplete
Oorzaak: JavaScript-rendered content, login walls

Fix:
→ Gebruik methode #1 (Duplicator) of #2 (FTP)
→ HTTrack is GEEN vervanging voor echte toegang!
```

### Issue #2: FTP Timeout / Incomplete
```
Symptoom: FileZilla stopt halverwege download
Oorzaak: Timeout, slechte verbinding

Fix:
# FileZilla Settings:
Edit → Settings → Connection
├─ Timeout: 300 seconds (was 20)
├─ Maximum retries: 10 (was 3)
└─ Retry delay: 5 seconds

# Of gebruik rsync (auto-resume)
```

### Issue #3: Database Import Error
```
Symptoom: "ERROR 1064 syntax error" tijdens mysql import
Oorzaak: Character encoding mismatch

Fix:
mysql -u bert_user -p --default-character-set=utf8mb4 bert_db < backup.sql

# Of edit backup.sql, add aan top:
SET NAMES utf8mb4;
SET CHARACTER SET utf8mb4;
```

### Issue #4: WordPress White Screen After Migration
```
Symptoom: Site laadt, maar alleen witte pagina

Fix #1: Check database credentials
nano /var/www/bertvanderheide.nl/wp-config.php
# DB_NAME, DB_USER, DB_PASSWORD correct?

Fix #2: Enable debug mode
define('WP_DEBUG', true);
define('WP_DEBUG_LOG', true);
# Check /wp-content/debug.log

Fix #3: Regenerate .htaccess
WordPress Admin → Settings → Permalinks → Save Changes

Fix #4: Check file permissions
chown -R www-data:www-data /var/www/bertvanderheide.nl/
chmod -R 755 /var/www/bertvanderheide.nl/
```

---

## 📊 Methode Vergelijking

```
┌─────────────┬──────────┬────────────┬──────────┬──────────┐
│ METHODE     │ COMPLETE │ MAKKELIJK  │ SNELHEID │ TOEGANG  │
├─────────────┼──────────┼────────────┼──────────┼──────────┤
│ Duplicator  │ ★★★★★    │ ★★★★★      │ ★★★★☆    │ WP Admin │
│ FTP+phpMy   │ ★★★★★    │ ★★★☆☆      │ ★★★☆☆    │ FTP/cPnl │
│ SSH/rsync   │ ★★★★★    │ ★★☆☆☆      │ ★★★★★    │ SSH      │
│ Provider BU │ ★★★★★    │ ★★★★☆      │ ★★☆☆☆    │ Email    │
│ HTTrack     │ ★☆☆☆☆    │ ★★★★☆      │ ★★☆☆☆    │ Geen!    │
└─────────────┴──────────┴────────────┴──────────┴──────────┘

AANBEVELING:
1. WordPress? → Duplicator (#1)
2. Andere CMS / geen WP admin? → FTP + phpMyAdmin (#2)
3. SSH beschikbaar? → rsync (#3)
4. Helemaal geen toegang? → Vraag backup provider (#4)
5. Echt geen andere optie? → HTTrack (#5) maar verwacht problemen
```

---

## 🎯 Voor Bert's Site Specifiek

**Acties:**

```bash
# 1. Check of het WordPress is
curl -I https://bertvanderheide.nl/wp-admin/
# 200 OK? → WordPress!
# 404? → Iets anders

# 2. Als WordPress:
#    Mail naar Bert:
#    "Mag ik WordPress admin toegang voor migratie?"
#    → Gebruik Duplicator methode (#1)

# 3. Als geen admin toegang:
#    Mail naar Bert:
#    "Mag ik FTP/cPanel toegang van je huidige host?"
#    → Gebruik FTP methode (#2)

# 4. Als helemaal geen toegang mogelijk:
#    Mail naar Bert's huidige host:
#    "Kan ik een backup krijgen voor migratie?"
#    → Gebruik provider backup (#4)
```

---

**📅 Versie:** 1.0
**🗓️ Datum:** 12 november 2025
**✍️ Auteur:** Henk + Claude
**🎯 Doel:** Betrouwbare website migratie voor klanten

---

## Quick Command Reference

```bash
# Check site type
curl -I https://site.nl/wp-admin/

# Download via SCP
scp -r user@oldserver:/path/* /local/path/

# Download via rsync (resumable!)
rsync -avz --progress user@oldserver:/path/ /local/path/

# Compress for upload
tar -czf site-backup.tar.gz /var/www/site/

# Database dump
mysqldump -u user -p database > backup.sql

# Database import
mysql -u user -p newdatabase < backup.sql

# Fix WordPress URLs
mysql -u user -p database
UPDATE wp_options SET option_value='https://newurl.nl' WHERE option_name IN ('siteurl','home');
```

**🚀 Succes met de migratie!**

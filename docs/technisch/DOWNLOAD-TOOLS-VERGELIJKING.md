# Website Download Tools - Complete Vergelijking

> **🎯 Welke tool wanneer gebruiken voor site migratie?**

---

## 📊 Snelle Beslisboom

```
START: Welke toegang heb je?
│
├─ WordPress admin login?
│  └─ ✅ Gebruik: Duplicator Plugin (GEEN extern programma!)
│
├─ FTP/SFTP toegang?
│  └─ ✅ Gebruik: FileZilla (extern programma)
│
├─ cPanel toegang?
│  └─ ✅ Gebruik: Browser (cPanel File Manager, GEEN programma!)
│
├─ SSH toegang?
│  └─ ✅ Gebruik: WinSCP of Command Line (extern programma)
│
└─ GEEN toegang?
   └─ ⚠️ Gebruik: HTTrack (extern programma) - maar incompleet!
```

---

## 1️⃣ Duplicator Plugin (WordPress Only)

### Type
```
☑️ WordPress Plugin (draait OP de oude site)
☐ Extern programma op je PC
☐ Online tool
```

### Installatie
```
GEEN installatie op JE PC nodig!
Plugin installeert IN WordPress (op oude server):

1. Login: https://bertvanderheide.nl/wp-admin/
2. WordPress menu: Plugins → Add New
3. Search: "Duplicator"
4. Install + Activate
5. Duplicator → Create New Package
```

### Wat download je?
```
2 files naar je PC:
├─ installer.php (1 MB)
└─ backup_20251112.zip (500MB - 5GB)
    ├─ /wp-content/ (themes, plugins, uploads)
    ├─ /wp-includes/
    ├─ database.sql ← DATABASE MEE! ✅
    └─ wp-config.php
```

### Gebruik (Stap-voor-Stap)
```
STAP 1 - Op oude site:
├─ Login WordPress admin
├─ Install Duplicator plugin
├─ Create package (15 min wachten)
└─ Download 2 files

STAP 2 - Op je PC:
├─ Je hebt nu: installer.php + ZIP
└─ Klaar voor upload!

STAP 3 - Upload naar nieuwe server:
# Via FileZilla of SCP:
Upload beide files naar: /var/www/bertvanderheide.nl/

STAP 4 - Installeren:
├─ Ga in browser naar: https://bertvanderheide.nl/installer.php
├─ Wizard volgen (5 minuten)
└─ Done! ✅
```

### Voordelen vs Nadelen
```
✅ VOORDELEN:
├─ Database automatisch mee
├─ Complete backup in 1 ZIP
├─ Installer doet werk voor je
├─ Geen technische kennis nodig
├─ 100% WordPress compatible
└─ Gratis versie is voldoende

❌ NADELEN:
├─ Alleen voor WordPress
├─ Vereist WP admin toegang
├─ Grote sites = lange wachttijd
└─ Hosting moet plugin toestaan (meestal OK)
```

### Kosten
```
FREE versie: Voldoende voor 99% sites
PRO versie: €69/jaar (niet nodig voor migraties)
```

---

## 2️⃣ FileZilla - FTP/SFTP Client

### Type
```
☐ WordPress Plugin
☑️ Extern programma op je PC
☐ Online tool
```

### Installatie
```
Download: https://filezilla-project.org/
Install: FileZilla-3.x-setup.exe (Windows)
Size: ~15 MB

Installation:
├─ Next → Next → Install
├─ Geen malware (officiële site!)
└─ Start FileZilla
```

### Wat download je?
```
Alle website files (GEEN database!):
├─ /public_html/
│   ├─ index.php / index.html
│   ├─ /wp-content/ (als WordPress)
│   ├─ /images/
│   ├─ /css/
│   ├─ /js/
│   ├─ .htaccess
│   └─ wp-config.php

⚠️ Database apart downloaden via phpMyAdmin!
```

### Gebruik (Stap-voor-Stap)
```
STAP 1 - Vraag aan klant:
├─ FTP Host: ftp.huidigehost.nl
├─ Username: bert_ftp
├─ Password: xxxxxxx
└─ Port: 21 (FTP) of 22 (SFTP - beter!)

STAP 2 - FileZilla openen:
┌────────────────────────────────────────┐
│ Host: ftp.huidigehost.nl               │
│ Username: bert_ftp                     │
│ Password: ******                       │
│ Port: 22 (SFTP) of 21 (FTP)            │
│ [Quick Connect]                        │
└────────────────────────────────────────┘

STAP 3 - Scherm split:
├─ Links: Je PC (C:\Temp\bert-site\)
└─ Rechts: Server (/public_html/)

STAP 4 - Download:
├─ Rechts: Select /public_html/ folder
├─ Rechtermuisklik → Download
├─ Wacht: 10-60 minuten
└─ Check: Alle files in C:\Temp\bert-site\ ?

STAP 5 - Database apart:
Via cPanel phpMyAdmin (zie sectie 4)
```

### Voordelen vs Nadelen
```
✅ VOORDELEN:
├─ Werkt voor ALLE site types (WP, Laravel, static)
├─ Directe file access
├─ Kan resume bij disconnect
├─ Overzichtelijke GUI
├─ Gratis & open source
└─ Zeer betrouwbaar

❌ NADELEN:
├─ Database NIET automatisch mee
├─ Moet apart credentials vragen
├─ Langzamer dan SSH/rsync
└─ Soms timeout bij grote sites
```

### Kosten
```
Gratis! Open source.
```

---

## 3️⃣ WinSCP - Windows SSH/SCP Client

### Type
```
☐ WordPress Plugin
☑️ Extern programma op je PC
☐ Online tool
```

### Installatie
```
Download: https://winscp.net/
Install: WinSCP-5.x-Setup.exe
Size: ~10 MB
```

### Wat download je?
```
Zelfde als FileZilla:
├─ Alle files
└─ GEEN database (apart via SSH of phpMyAdmin)
```

### Gebruik (Stap-voor-Stap)
```
Zelfde als FileZilla, maar:
├─ Betere SSH key support
├─ Ingebouwde text editor
├─ Commander-style interface (als Total Commander)
└─ SCP protocol (sneller dan SFTP)

Connect:
Protocol: SFTP of SCP
Host: ssh.huidigehost.nl
Port: 22
Username: bert_ssh
Password: ****
```

### FileZilla vs WinSCP?
```
FileZilla:
├─ Simpeler interface
├─ Meer verspreid
└─ Beter voor beginners

WinSCP:
├─ Beter voor SSH keys
├─ Commander UI (2 panels)
├─ Ingebouwde editor
└─ Sneller met SCP protocol
```

### Kosten
```
Gratis! Open source.
```

---

## 4️⃣ cPanel File Manager (Browser - GEEN programma!)

### Type
```
☐ WordPress Plugin
☐ Extern programma
☑️ Online tool (in browser)
```

### Toegang
```
Vraag aan klant:
├─ cPanel URL: https://huidigehost.nl:2083
├─ Username: bert_cpanel
└─ Password: ******
```

### Wat download je?
```
Via File Manager:
├─ ZIP van alle files maken
├─ ZIP downloaden
└─ Op je PC uitpakken

Via phpMyAdmin (in cPanel):
└─ Database .sql export
```

### Gebruik (Stap-voor-Stap)
```
FILES:
1. Login cPanel
2. File Manager icon
3. Navigate to: public_html/
4. Select All
5. Right click → Compress → ZIP
6. Wait... (5-15 min)
7. Right click ZIP → Download
8. Extract lokaal op PC

DATABASE:
1. cPanel → phpMyAdmin icon
2. Select database (left menu)
3. Tab: Export
4. Method: Quick
5. Format: SQL
6. Click: Export
7. Download: database.sql
```

### Voordelen vs Nadelen
```
✅ VOORDELEN:
├─ Geen software installeren
├─ Werkt in browser
├─ ZIP maken server-side (sneller!)
├─ Database + files in 1 interface
└─ Vaak beschikbaar bij shared hosting

❌ NADELEN:
├─ Vereist cPanel toegang
├─ Timeout bij zeer grote sites
├─ 1 grote ZIP = alles of niets (geen resume)
└─ Browser kan crashen bij grote downloads
```

### Kosten
```
Gratis (onderdeel van cPanel hosting)
```

---

## 5️⃣ Command Line - SSH/rsync/scp

### Type
```
☐ WordPress Plugin
☑️ Extern programma / ingebouwd in Windows
☐ Online tool
```

### Installatie
```
Windows 10/11:
├─ SSH: Built-in in PowerShell ✅
├─ SCP: Built-in in PowerShell ✅
└─ rsync: Installeer via Git for Windows

Git for Windows:
Download: https://git-scm.com/
Install → Krijg je: Git Bash (inclusief rsync!)
```

### Gebruik (Stap-voor-Stap)
```
Via PowerShell of Git Bash:

METHODE A - SCP (simpel):
scp -r bert@oudehost.nl:/home/bert/public_html/* C:/Temp/bert-site/

METHODE B - rsync (beter - kan resume!):
rsync -avz --progress bert@oudehost.nl:/home/bert/public_html/ C:/Temp/bert-site/

DATABASE:
ssh bert@oudehost.nl
mysqldump -u db_user -p database > backup.sql
exit
scp bert@oudehost.nl:backup.sql C:/Temp/
```

### Voordelen vs Nadelen
```
✅ VOORDELEN:
├─ Snelste methode!
├─ rsync = kan resume
├─ Automatiseerbaar (script)
├─ Geen GUI overhead
├─ Professional
└─ Permissions blijven behouden

❌ NADELEN:
├─ Vereist SSH toegang
├─ Command line kennis nodig
├─ Intimidating voor beginners
└─ Windows = extra setup (Git Bash)
```

### Kosten
```
Gratis (built-in of via Git for Windows)
```

---

## 6️⃣ HTTrack - Website Copier

### Type
```
☐ WordPress Plugin
☑️ Extern programma op je PC
☐ Online tool
```

### Installatie
```
Download: https://www.httrack.com/
Install: httrack-3.x.exe (Windows)
Size: ~5 MB
```

### Wat download je?
```
⚠️ ALLEEN wat een browser ziet:
├─ HTML files (statisch gegenereerd)
├─ CSS
├─ JavaScript
├─ Images
└─ PDFs

❌ NIET gedownload:
├─ Database (!!!)
├─ PHP backend
├─ WordPress admin
├─ .htaccess
├─ wp-config.php
└─ Dynamische content
```

### Gebruik (Stap-voor-Stap)
```
1. Open HTTrack
2. Project name: bert-site
3. Base path: C:\Temp\httrack\
4. Web Address: https://bertvanderheide.nl
5. Options:
   ├─ Scan rules: +*bertvanderheide.nl/*
   ├─ No external links
   └─ Depth: 5 levels
6. Start mirror
7. Wait: 30-120 min
8. Result: Static HTML copy

⚠️ Dit is GEEN werkende WordPress site!
   Alleen HTML snapshot!
```

### Voordelen vs Nadelen
```
✅ VOORDELEN:
├─ Geen toegang nodig
├─ Werkt altijd (publiek crawlbaar)
├─ Makkelijk te gebruiken
└─ Goed voor static backup

❌ NADELEN:
├─ GEEN database
├─ GEEN PHP/backend
├─ Formulieren werken niet
├─ Admin area niet mee
├─ WordPress plugins weg
├─ Alleen geschikt voor "foto" van site
└─ Moet handmatig reconstrueren naar werkende site
```

### Kosten
```
Gratis! Open source.
```

---

## 📊 Vergelijkingstabel

```
┌──────────────┬────────┬──────────┬──────────┬──────────┬────────────┐
│ TOOL         │ FILES  │ DATABASE │ TOEGANG  │ MOEILIJK │ VOLLEDIG   │
├──────────────┼────────┼──────────┼──────────┼──────────┼────────────┤
│ Duplicator   │ ✅ Ja  │ ✅ Auto  │ WP Admin │ ⭐ Makkelijk│ ✅ 100%  │
│ FileZilla    │ ✅ Ja  │ ❌ Nee   │ FTP/SFTP │ ⭐⭐ OK    │ ⚠️ 90%   │
│ WinSCP       │ ✅ Ja  │ ❌ Nee   │ SSH/SFTP │ ⭐⭐ OK    │ ⚠️ 90%   │
│ cPanel       │ ✅ Ja  │ ✅ Apart │ cPanel   │ ⭐ Makkelijk│ ✅ 95%   │
│ SSH/rsync    │ ✅ Ja  │ ❌ Nee   │ SSH      │ ⭐⭐⭐ Hard │ ⚠️ 90%   │
│ HTTrack      │ ⚠️ HTML│ ❌ Nee   │ Geen!    │ ⭐ Makkelijk│ ❌ 30%   │
└──────────────┴────────┴──────────┴──────────┴──────────┴────────────┘
```

---

## 🎯 Aanbeveling per Scenario

### SCENARIO 1: WordPress + Je hebt admin login
```
✅ Gebruik: Duplicator Plugin
Waarom: 100% compleet, automatisch, makkelijk
Tools: Alleen browser nodig
Tijd: 30 minuten
```

### SCENARIO 2: WordPress + Geen admin, wel FTP
```
✅ Gebruik: FileZilla + cPanel phpMyAdmin
Waarom: Complete files + database
Tools: FileZilla installeren
Tijd: 60 minuten
```

### SCENARIO 3: Niet-WordPress + FTP toegang
```
✅ Gebruik: FileZilla + phpMyAdmin/SSH dump
Waarom: Universeel, werkt altijd
Tools: FileZilla installeren
Tijd: 60 minuten
```

### SCENARIO 4: SSH toegang beschikbaar
```
✅ Gebruik: rsync/scp (command line)
Waarom: Snelste, meest betrouwbaar
Tools: Git Bash (voor rsync)
Tijd: 20 minuten
```

### SCENARIO 5: Alleen cPanel toegang
```
✅ Gebruik: cPanel File Manager + phpMyAdmin
Waarom: Alles in browser, geen installatie
Tools: Alleen browser
Tijd: 45 minuten
```

### SCENARIO 6: Helemaal geen toegang
```
⚠️ Gebruik: HTTrack (maar verwacht problemen!)
Waarom: Last resort, incompleet
Tools: HTTrack installeren
Tijd: 2 uur + handmatig herstel werk
```

---

## 💾 Installatie Checklist

**Minimale Setup (FileZilla):**
```bash
# 1. Download FileZilla
https://filezilla-project.org/download.php?type=client

# 2. Install
FileZilla_3.x_win64-setup.exe
├─ Next → Next → Install
└─ ⚠️ Weiger toolbars/extra's tijdens install!

# 3. Test
Open FileZilla → Settings → Interface
Taal: Nederlands (optioneel)
```

**Gevorderd Setup (Command Line):**
```bash
# 1. Install Git for Windows
https://git-scm.com/download/win

# 2. During install:
├─ Select: "Git Bash Here"
├─ Select: "Use Windows' default console"
└─ Install

# 3. Test
Git Bash openen:
rsync --version
ssh -V
scp
```

---

## 🔧 Snelle Vergelijking: Wat Moet Ik Installeren?

```
Als je WordPress admin hebt:
└─ NIETS! Duplicator plugin installeert IN WordPress

Als je FTP toegang hebt:
└─ FileZilla (15 MB, 5 min installatie)

Als je cPanel hebt:
└─ NIETS! Werkt in browser

Als je SSH hebt en command line durft:
└─ Git for Windows (voor rsync, 80 MB)

Als je helemaal geen toegang hebt:
└─ HTTrack (5 MB) maar verwacht problemen
```

---

## 📞 Quick Decision Guide

```
Vraag aan klant: "Welke toegang kan je geven?"

A. WordPress admin login
   → Duplicator (NIETS installeren)

B. FTP/SFTP inloggegevens
   → FileZilla (15 MB download)

C. cPanel login
   → Browser (NIETS installeren)

D. SSH toegang
   → Git Bash (als je command line kent)

E. Geen enkele toegang mogelijk
   → Vraag klant om backup bij huidige host
   → Last resort: HTTrack (incompleet)
```

---

**📅 Versie:** 1.0
**🗓️ Datum:** 12 november 2025
**🎯 Conclusie:** Duplicator (WordPress) of FileZilla (overig) zijn de beste keuzes!


# 🔧 Technische Documentatie

> **Server setup, migratie methoden en troubleshooting**

---

## 📋 Documenten

### [VPS-GEGEVENS-OVERZICHT.md](VPS-GEGEVENS-OVERZICHT.md)
**Wat:** Complete server setup documentatie
**Gebruik:** Wanneer je server info nodig hebt of nieuwe sites wilt toevoegen
**Inhoud:**
- Hetzner VPS specificaties
- Apache VirtualHost configuratie
- MySQL database setup
- SSL certificaten (Let's Encrypt)
- Huidige sites overzicht
- SSH toegang info

---

### [WEBHOSTING-NIEUWE-SITE.md](WEBHOSTING-NIEUWE-SITE.md)
**Wat:** Stap-voor-stap guide om nieuwe site toe te voegen
**Gebruik:** Bij elke nieuwe klant/site
**Inhoud:**
- Directory aanmaken
- Apache VirtualHost configureren
- Database aanmaken
- DNS instellingen
- SSL certificaat installeren
- WordPress deployment
- Testing checklist

---

### [SITE-MIGRATIE-METHODEN.md](SITE-MIGRATIE-METHODEN.md)
**Wat:** Vergelijking van alle migratie methoden
**Gebruik:** Wanneer je een bestaande site moet migreren
**Inhoud:**
- **Methode 1:** Duplicator plugin (WordPress, aanbevolen)
- **Methode 2:** FTP + cPanel (universeel)
- **Methode 3:** rsync + mysqldump (advanced)
- **Methode 4:** HTTrack (alleen HTML, NIET voor WordPress!)
- Voor/nadelen per methode
- Tijdsinvestering per methode

**→ Conclusie:** Duplicator voor WordPress, FTP voor rest

---

### [DOWNLOAD-TOOLS-VERGELIJKING.md](DOWNLOAD-TOOLS-VERGELIJKING.md)
**Wat:** Vergelijking FTP tools en download tools
**Gebruik:** Wanneer je niet zeker weet welke tool te gebruiken
**Inhoud:**
- FileZilla (gratis, cross-platform)
- WinSCP (Windows, scripting mogelijk)
- HTTrack (website copier, ALLEEN voor statische HTML)
- cPanel File Manager (via browser)
- Commandline tools (scp, rsync)

**→ Aanbeveling:** FileZilla voor FTP, Duplicator voor WordPress

---

### [FILAMENT-WORKFLOW-BERT.md](FILAMENT-WORKFLOW-BERT.md)
**Wat:** Hoe Bert en Henk samenwerken met Laravel + Filament
**Gebruik:** Training voor Bert, referentie voor content beheer
**Inhoud:**
- Verschil WordPress vs Filament (simpeler!)
- Wat Bert kan doen (content, blog, FAQ)
- Wat Bert NIET hoeft te doen (SEO, plugins, updates)
- Staging vs Production workflow
- Praktische tips voor dagelijks gebruik

**→ Key Takeaway:** Filament = alleen de knoppen die Bert nodig heeft, Claude doet de rest

---

### [WAAROM-SCRAPING-NIET-WERKT.md](WAAROM-SCRAPING-NIET-WERKT.md)
**Wat:** Uitleg waarom je site niet "gewoon kunt downloaden"
**Gebruik:** Historische referentie (minder relevant nu we zelf bouwen)
**Inhoud:**
- Verschil HTML (output) vs Database (backend)
- Wat scraping tools WEL downloaden (HTML, CSS, JS, images)
- Wat scraping tools NIET downloaden (database, PHP, wp-config)
- Waarom database NOOIT publiek toegankelijk is (security)

**→ Note:** Met onze nieuwe aanpak (zelf bouwen) is migratie niet meer nodig!

---

## 🎯 Workflow: Nieuwe Laravel + Filament Site Bouwen

**Stap 1:** Content verzamelen van klant (teksten, foto's, logo)

**Stap 2:** Laravel project opzetten + Filament installeren

**Stap 3:** Claude bouwt site met SEO (automatisch correct!)

**Stap 4:** Deploy op server via [WEBHOSTING-NIEUWE-SITE.md](WEBHOSTING-NIEUWE-SITE.md)

**Stap 5:** Training klant via [FILAMENT-WORKFLOW-BERT.md](FILAMENT-WORKFLOW-BERT.md)

---

## 🎯 Workflow (Legacy): WordPress Site Migreren

> **Let op:** Deze workflow is alleen nog relevant als een klant per se WordPress wil.
> Voor nieuwe klanten: gebruik Laravel + Filament!

**Stap 1:** Lees [WAAROM-SCRAPING-NIET-WERKT.md](WAAROM-SCRAPING-NIET-WERKT.md)

**Stap 2:** Vraag toegang via [../business/EMAIL-TEMPLATES-MIGRATIE.md](../business/EMAIL-TEMPLATES-MIGRATIE.md)

**Stap 3:** Gebruik Duplicator methode uit [SITE-MIGRATIE-METHODEN.md](SITE-MIGRATIE-METHODEN.md)

---

## 🚨 Belangrijke Waarschuwingen

⚠️ **NOOIT** HTTrack gebruiken voor WordPress sites (geen database!)
⚠️ **ALTIJD** backup maken voor wijzigingen aan Apache config
⚠️ **CONTROLEER** DNS voordat je live gaat (www + root domain)
⚠️ **TEST** SSL certificaat na installatie (https://www.ssllabs.com/ssltest/)

---

[← Terug naar Docs](../README.md) | [← Terug naar Hoofdmenu](../../README.md)

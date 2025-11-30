# 🎯 Project: Bert van der Heide Uitvaartzorg

> **Website hosting + SEO pakket voor uitvaartondernemer in Enschede**
>
> **Status:** 🟡 Voorbereiding (nog geen contact met klant)
> **Verwachte waarde:** €350/maand recurring + €350 eenmalig

---

## 📋 Project Informatie

### Klant Details
```
Bedrijf: Bert van der Heide Uitvaartzorg
Adres: Livingstonestraat 44, 7532 CJ Enschede
Telefoon: 06 81026062 (24/7 bereikbaar)
Website: bertvanderheide.nl
Team: Bert van der Heide + zoon Koen
Ervaring: 16 jaar bedrijf, 35 jaar totaal
Sector: Uitvaartondernemer
```

### Huidige Situatie (Analyse)
```
Provider: Mooi Online (mooionline.nl)
Server IP: 84.247.13.197 (LiteSpeed)
CMS: WordPress 6.8.3 + Yoast SEO 26.4
Huidige kosten: €700/maand
Analytics: Google Analytics actief (G-V0KDW6CVRG)
```

### SEO Analyse Resultaat
```
Score: 6/10 (basis aanwezig, veel verbeterpotentieel)

✅ Goed:
- WordPress met Yoast SEO
- SSL/HTTPS actief
- Responsive design
- WP Rocket caching

❌ Kritieke issues:
- Title tag: "Bert van der Heide Uitvaartzorg" (mist lokale keywords!)
- H1: "Voor een waardevol afscheid" (geen keywords)
- Schema.org: Organization (moet FuneralHome zijn)
- Google My Business: Bestaat, maar check of geclaimd/geoptimaliseerd
- Geen blog of content strategie
- Geen FAQ pagina

✅ Online aanwezigheid:
- Trustoo: 9,6/10 (16 reviews) - Premium Partner
- Google Maps vermelding aanwezig
- uitvaartverzorging-info.nl vermelding

→ Volledige audit: ../../docs/seo/SEO-AUDIT-bertvanderheide.md
```

---

## 📁 Project Bestanden

### Overzicht Deze Map
```
projecten/bert-van-der-heide/
├── README.md (← JE BENT HIER)
├── Hosten op havun.md (braindump sessie 9 nov)
├── home-content.html (homepage scrape voor referentie)
└── documentatie/
    ├── offerte-bert.md (hosting pakket €350 + €350/maand)
    └── intake-checklist.md (voor eerste gesprek)
```

### Gerelateerde Docs (Buiten Project)
```
SEO Specifiek:
→ ../../docs/seo/SEO-AUDIT-bertvanderheide.md (12.000+ woorden analyse)
→ ../../docs/seo/OFFERTE-SEO-bertvanderheide.md (3 SEO pakketten - ALLEEN als geen hosting)
→ ../../docs/seo/GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md

Technisch:
→ ../../docs/technisch/SITE-MIGRATIE-METHODEN.md
→ ../../docs/technisch/WAAROM-SCRAPING-NIET-WERKT.md

Business:
→ ../../docs/business/EMAIL-TEMPLATES-MIGRATIE.md
```

---

## 🎯 STRATEGIE: Hosting + SEO Pakket

**Waarom dit beter is:**
```
✅ Volledige controle - Direct aanpassingen maken
✅ Snellere SEO implementatie - Geen wachten op Mooi Online
✅ Complete service - 1 aanspreekpunt voor Bert
✅ Hogere marge - €350 vs €295 (alleen SEO)
✅ Professioneler - Alles uit eigen hand

❌ SEO zonder hosting = Gedoe met Mooi Online bij elke wijziging
```

---

## 💰 Offerte Structuur

### Eenmalig
```
Website bouwen: €350 (eerste klant/leergeld)
├─ Nieuwe professionele website (Laravel + Filament)
├─ Alle content overnemen
├─ Mobile responsive design
├─ Contactformulier met notificaties
├─ Google Maps integratie
└─ Simpel beheerpaneel

TOTAAL EENMALIG: €350
```

### Maandelijks
```
Website + SEO pakket: €350/maand
├─ Hosting (Hetzner VPS share)
├─ Domain DNS beheer
├─ Website onderhoud
├─ Security updates
├─ Dagelijkse backups
├─ Actieve SEO (zie hieronder)
├─ Support (24u response)
└─ Maandelijkse rapportage

Email (direct aan Google): €6/maand
└─ Klant betaalt Google rechtstreeks

TOTAAL MAANDELIJKS: €356/maand
BESPARING voor klant: €344/maand = €4.128/jaar! 🎉
```

---

## 🖥️ Technische Setup

### Server Informatie
```
Provider: Hetzner Cloud
IP: 188.245.159.115
OS: Ubuntu 22.04 LTS
Web Server: Apache 2.4
PHP: 8.2
Database: MySQL 8.x
SSL: Let's Encrypt (gratis)
```

### Site Locatie
```
Server Path: /var/www/bertvanderheide.nl/
DocumentRoot: /var/www/bertvanderheide.nl/public/
VirtualHost: /etc/apache2/sites-available/bertvanderheide.nl.conf
Database: bert_db
DB User: bert_user
SSL Cert: /etc/letsencrypt/live/bertvanderheide.nl/
```

### DNS Configuratie
```
A-record:
@ → 188.245.159.115

CNAME:
www → bertvanderheide.nl

MX-records (Google Workspace):
@ → 1  → smtp.google.com
@ → 5  → alt1.gmr-smtp-in.l.google.com
@ → 10 → alt2.gmr-smtp-in.l.google.com

TXT (SPF):
@ → v=spf1 include:_spf.google.com ~all

TXT (Google Verification):
@ → google-site-verification=xxxxx (na setup)
```

---

## 🎯 SEO Strategie

### Lokale SEO Focus (Twente Regio)

#### Target Keywords
```
Primary:
├─ "uitvaartondernemer enschede"
├─ "crematie hengelo"
├─ "uitvaart kosten twente"
├─ "begrafenis regelen almelo"
└─ "uitvaartondernemer oldenzaal"

Long-tail:
├─ "wat kost een uitvaart in enschede"
├─ "uitvaartondernemer enschede 24 uur"
├─ "goedkope uitvaart twente"
├─ "persoonlijke uitvaart enschede"
└─ "crematie zonder kist mogelijk"
```

#### Service Areas
```
Primair: Enschede
Secundair: Hengelo, Almelo, Oldenzaal, Borne, Losser
```

### Google My Business Setup
```
□ Account claimen/aanmaken
□ Volledig profiel invullen
  ├─ Bedrijfsinfo, openingstijden (24/7)
  ├─ Service areas (Enschede, Hengelo, Almelo, etc)
  ├─ Categories: Funeral Home, Cremation Service
  └─ Attributes (parking, accessibility)
□ Foto's uploaden (10-15)
  ├─ Exterior/interior
  ├─ Team (Bert & Koen)
  └─ Services voorbeelden
□ Q&A pre-seeden (10 vragen)
□ Wekelijkse posts strategie
□ Review request systeem opzetten
```

### Content Planning

#### Foundational Pages (Maand 1)
```
1. Homepage
2. Over Ons / Team
3. Diensten
   ├─ Begrafenis
   ├─ Crematie
   ├─ Persoonlijke uitvaart
   └─ Nazorg
4. Wat kost een uitvaart
5. Veel gestelde vragen (FAQ)
6. Contact
7. Blog overzicht
8. Privacy & Cookies
```

#### Blog Posts (Maand 1-3)
```
1. "Wat kost een uitvaart in Enschede?" (SEO goud!)
2. "Checklist: wat te doen bij overlijden in Twente"
3. "Crematie vs Begrafenis: kosten en verschillen"
4. "Hoe kies je een uitvaartondernemer in Hengelo?"
5. "Uitvaartverzekering: wat dekt het wel/niet?"
6. "Persoonlijke uitvaart ideeën en voorbeelden"
7. "24/7 bereikbaar bij overlijden: hoe werkt dat?"
8. "Uitvaart regelen in coronatijd: wat is er veranderd?"
```

#### Ongoing Content (Maand 4+)
```
Frequency: 1 blog post per maand (400-600 woorden)
Google My Business: 4 posts per maand (wekelijks)
```

### Technische SEO Checklist
```
□ Google Search Console setup
□ Google Analytics 4 setup
□ XML Sitemap genereren
□ Robots.txt configureren
□ Schema.org markup (FuneralHome type)
□ Meta descriptions (alle pagina's)
□ Alt-tags (alle afbeeldingen)
□ Page speed optimization
  ├─ Image compression
  ├─ Lazy loading
  └─ Minify CSS/JS
□ Mobile-first responsive check
□ SSL/HTTPS redirect
□ Structured data testing
```

---

## 📅 Project Timeline

### Week 1: Intake & Analyse
```
□ Eerste gesprek met Bert
□ Toegang verkrijgen (WordPress/FTP/cPanel)
□ Analyse huidige site
  ├─ CMS detectie
  ├─ Content inventory
  ├─ Functionaliteiten
  └─ Huidige SEO status
□ Email huidige setup checken
□ DNS huidige configuratie documenteren
```

### Week 2-3: Migratie & Bouw
```
□ Complete backup oude site (Duplicator/FTP)
□ Server setup
  ├─ Directory aanmaken
  ├─ Apache VirtualHost
  ├─ Database aanmaken
  └─ SSL certificaat
□ Site deployment
□ Content migratie
□ Design modernisering (indien nodig)
□ Functionaliteiten testen
```

### Week 4: SEO Foundation
```
□ Google Search Console
□ Google Analytics 4
□ Google My Business setup
□ Schema.org markup
□ XML Sitemap
□ Meta descriptions
□ Page speed optimization
□ Content foundation (6-8 blog posts)
```

### Week 5: Testing & Go-Live
```
□ Staging URL delen met klant
□ Feedback verwerken
□ Final testing
  ├─ Alle pagina's
  ├─ Contactformulier
  ├─ Mobile responsive
  └─ Browser compatibility
□ DNS switch voorbereiden
□ Go-Live!
```

### Week 6+: Ongoing
```
Maandelijks:
├─ 1 blog post (AI-assisted)
├─ 4 GMB posts (wekelijks)
├─ Rankings monitoring
├─ Traffic analyse
├─ Maandrapportage
└─ Support & onderhoud
```

---

## 📁 Project Structure

```
SEOBertvanderHeide/
├── website/              # Website bestanden (na migratie)
│   ├── public/          # DocumentRoot
│   ├── storage/         # Logs, cache
│   └── database/        # Database dumps
│
├── documentatie/        # Project documentatie
│   ├── offerte.md
│   ├── intakegesprek.md
│   ├── content-inventory.md
│   └── seo-strategy.md
│
├── assets/              # Design assets
│   ├── logo/
│   ├── images/
│   └── screenshots/
│
├── backups/             # Lokale backups
│   ├── old-site/
│   └── database/
│
└── README.md            # Dit bestand
```

---

## 🔐 Credentials (VERTROUWELIJK)

### WordPress Admin (Na Migratie)
```
URL: https://bertvanderheide.nl/wp-admin/
Username: [Te bepalen]
Password: [Te bepalen]
```

### Database
```
Host: localhost (127.0.0.1)
Database: bert_db
Username: bert_user
Password: [Te bepalen - sterk wachtwoord]
```

### Google Workspace
```
Email: info@bertvanderheide.nl
Admin: [Bert's Google account]
Password: [Bert beheert zelf]
```

### SSH Server Access
```
Host: 188.245.159.115
User: root
Key: C:\Users\henkv\.ssh\id_ed25519
```

---

## 📞 Contacten

### Klant
```
Naam: Bert van der Heide (+ zoon Koen)
Bedrijf: Bert van der Heide Uitvaartzorg
Telefoon: 06 81026062
Adres: Livingstonestraat 44, 7532 CJ Enschede
Email: [Te verkrijgen]
```

### Jouw Gegevens
```
Naam: Henk
Bedrijf: Havun Web Services
Email: havun22@gmail.com
Telefoon: [Je nummer]
```

---

## ✅ Status Tracker

### Project Fase
```
[ ] Sales / Offerte
[ ] Intake
[ ] Migratie
[ ] Testing
[ ] Live
[X] Ongoing Onderhoud
```

### Toegang Verkregen
```
[ ] WordPress admin
[ ] FTP/SFTP
[ ] cPanel
[ ] Database
[ ] DNS beheer
[ ] Email admin
```

### Technical Setup
```
[ ] Server directory
[ ] Apache VirtualHost
[ ] Database aangemaakt
[ ] SSL certificaat
[ ] DNS A-record
[ ] Google Workspace
[ ] Google My Business
[ ] Google Analytics
[ ] Google Search Console
```

---

## 📊 Success Metrics

### Maand 1-3 (Setup Fase)
```
Target:
├─ Site live en volledig functioneel
├─ Google My Business actief
├─ 6-8 foundational blog posts
├─ Basis rankings voor brand keywords
└─ 50-100 bezoekers/maand (baseline)
```

### Maand 4-6 (Growth Fase)
```
Target:
├─ Top 10 rankings voor 2-3 local keywords
├─ 100-200 bezoekers/maand
├─ 5+ Google My Business reviews
├─ Contactformulier conversies: 2-5/maand
└─ Organisch traffic groei: +50%
```

### Maand 7-12 (Mature Fase)
```
Target:
├─ Top 5 rankings voor primaire keywords
├─ 200-500 bezoekers/maand
├─ 10+ Google reviews (4.5+ gemiddeld)
├─ Contactformulier conversies: 5-10/maand
└─ Stabiele #1-3 posities lokaal
```

---

**📅 Document Versie:** 1.1
**🗓️ Aangemaakt:** November 2025
**🗓️ Laatst bijgewerkt:** 26 november 2025
**✍️ Auteur:** Henk - Havun Web Services
**🎯 Status:** In voorbereiding

---

## ⚠️ TECHNISCHE KEUZE UPDATE (26 nov 2025)

**Besluit: GEEN WordPress, maar Laravel + Filament**

Zie: [documentatie/TECHNISCHE-KEUZE.md](documentatie/TECHNISCHE-KEUZE.md)

Reden:
- Volledige controle (Henk + Claude Code)
- Supersimpel admin panel voor Bert
- Geen licentie issues met thema's
- Snellere site, minder onderhoud

---

## 🚀 Next Steps & Action Plan

### STAP 1: Eerste Contact (Deze Week)
```
□ Bellen met Bert - Offerte bespreken
□ Uitleggen huidige situatie (€700/maand → €350/maand)
□ SEO potentieel laten zien (Top 3 rankings mogelijk)
□ Keuze laten maken: Hosting + SEO pakket

Documenten te gebruiken:
→ documentatie/offerte-bert.md (hosting pakket)
→ ../../docs/seo/OFFERTE-SEO-bertvanderheide.md (SEO pakketten)
→ ../../docs/seo/SEO-AUDIT-bertvanderheide.md (laten zien wat we gevonden hebben)
```

### STAP 2: Intake Gesprek (Week 2)
```
□ Gebruik intake-checklist.md
□ Bedrijfsinformatie verzamelen
□ Toegang regelen (3 opties)
□ Foto's/materiaal ontvangen

Documenten te gebruiken:
→ documentatie/intake-checklist.md
→ ../../docs/business/EMAIL-TEMPLATES-MIGRATIE.md (toegang vragen)
→ ../../docs/seo/GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md (GSC setup)
```

### STAP 3: Migratie (Week 3-4)
```
□ Toegang via Mooi Online of WordPress admin
□ Duplicator plugin gebruiken (aanbevolen)
□ Deploy op Hetzner server (188.245.159.115)
□ Testing op staging URL

Documenten te gebruiken:
→ ../../docs/technisch/SITE-MIGRATIE-METHODEN.md
→ ../../docs/technisch/WEBHOSTING-NIEUWE-SITE.md
→ ../../docs/technisch/VPS-GEGEVENS-OVERZICHT.md
```

### STAP 4: SEO Implementatie (Week 5-8)
```
□ Quick Wins (Title, H1, Schema.org, GMB)
□ FAQ pagina aanmaken
□ 6-8 blog posts schrijven
□ Google Search Console + Analytics

Documenten te gebruiken:
→ ../../docs/seo/SEO-AUDIT-bertvanderheide.md (FASE 1 & 2)
```

### STAP 5: Go-Live & Ongoing (Week 9+)
```
□ DNS switch
□ Monitoring eerste week
□ Maandelijkse SEO service starten
□ €350/maand recurring! 🎉

Documenten te gebruiken:
→ ../../docs/business/EMAIL-TEMPLATES-MIGRATIE.md (templates #8, #9, #10)
```

---

## 🔗 Snelle Links

**Voor klantgesprek:**
- [Hosting Offerte](documentatie/offerte-bert.md)
- [SEO Offerte (3 pakketten)](../../docs/seo/OFFERTE-SEO-bertvanderheide.md)
- [SEO Audit (toon potentie)](../../docs/seo/SEO-AUDIT-bertvanderheide.md)

**Voor implementatie:**
- [Migratie Methoden](../../docs/technisch/SITE-MIGRATIE-METHODEN.md)
- [Email Templates](../../docs/business/EMAIL-TEMPLATES-MIGRATIE.md)
- [Server Setup](../../docs/technisch/VPS-GEGEVENS-OVERZICHT.md)

**Voor SEO werk:**
- [Complete SEO Workflow](../../docs/seo/README.md)
- [Google Search Console Setup](../../docs/seo/GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md)

---

[← Terug naar Projecten](../) | [← Terug naar Hoofdmenu](../../README.md)

**Let's go!** 💪

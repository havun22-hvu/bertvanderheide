# 📂 Directory Structuur Overzicht

> **Hiërarchische navigatie guide voor Claude en ontwikkelaars**

---

## 🎯 Leeswijzer voor Claude

**Bij nieuwe conversatie, lees in deze volgorde:**

1. **START HIER:** `/README.md` (hoofdoverzicht, 5 min lezen)
2. **Als technische vraag:** `/docs/technisch/README.md` → specifiek MD bestand
3. **Als business vraag:** `/docs/business/README.md` → templates
4. **Als SEO vraag:** `/docs/seo/README.md` → audit/offerte
5. **Voor project Bert:** `/projecten/bert-van-der-heide/README.md`

**→ Lees NOOIT alle MD files tegelijk (te veel context!)**
**→ Start altijd met README, navigeer naar details**

---

## 📁 Complete Directory Tree

```
BertvanderHeide/
│
├── 📄 README.md                           ← START HIER (hoofdoverzicht)
├── 📄 STRUCTURE.md                        ← Deze file (navigatie guide)
├── 📄 .gitignore                          ← Git ignore regels
│
├── 📁 website/                            ← Laravel + Filament code
│   └── (Laravel project)
│
├── 📁 docs/                               ← Algemene documentatie
│   ├── 📄 README.md                       ← Docs overzicht
│   │
│   ├── 📁 technisch/                      ← Server, migratie, tools
│   │   ├── 📄 README.md                   ← Technische docs index
│   │   ├── 📄 VPS-GEGEVENS-OVERZICHT.md   (Server specs, SSH, Nginx)
│   │   ├── 📄 WEBHOSTING-NIEUWE-SITE.md   (Stappen nieuwe site toevoegen)
│   │   ├── 📄 SITE-MIGRATIE-METHODEN.md   (Duplicator vs FTP vs rsync)
│   │   ├── 📄 DOWNLOAD-TOOLS-VERGELIJKING.md (FileZilla, WinSCP, HTTrack)
│   │   ├── 📄 FILAMENT-WORKFLOW-BERT.md   (Hoe Bert admin panel gebruikt)
│   │   └── 📄 WAAROM-SCRAPING-NIET-WERKT.md (Database vs HTML uitleg)
│   │
│   ├── 📁 business/                       ← Templates, processen
│   │   ├── 📄 README.md                   ← Business docs index
│   │   └── 📄 EMAIL-TEMPLATES-MIGRATIE.md (10 email templates)
│   │
│   └── 📁 seo/                            ← SEO strategieën, audits
│       ├── 📄 README.md                   ← SEO docs index
│       ├── 📄 SEO-AUDIT-bertvanderheide.md (12.000+ woorden template)
│       ├── 📄 OFFERTE-SEO-bertvanderheide.md (3 pakketten template)
│       └── 📄 GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md (GSC setup)
│
└── 📁 projecten/                          ← Client projecten
    ├── 📄 README.md                       ← Projecten overzicht
    │
    └── 📁 bert-van-der-heide/             ← Project: Bert van der Heide
        ├── 📄 README.md                   ← Project overzicht (start hier!)
        ├── 📄 Hosten op havun.md          (Sessie braindump 9 nov)
        ├── 📄 home-content.html           (Homepage scrape referentie)
        │
        └── 📁 documentatie/
            ├── 📄 offerte-bert.md         (Hosting €350 + €350/maand)
            └── 📄 intake-checklist.md     (Eerste gesprek checklist)
```

---

## 🔍 Snelle Navigatie Per Taak

### "Ik moet een nieuwe WordPress site migreren"
```
1. Lees: /docs/technisch/README.md (workflow sectie)
2. Kies methode: /docs/technisch/SITE-MIGRATIE-METHODEN.md
3. Vraag toegang: /docs/business/EMAIL-TEMPLATES-MIGRATIE.md
4. Deploy: /docs/technisch/WEBHOSTING-NIEUWE-SITE.md
```

### "Ik moet een SEO offerte maken"
```
1. Lees: /docs/seo/README.md (workflow sectie)
2. Doe audit: /docs/seo/SEO-AUDIT-bertvanderheide.md (als template)
3. Maak offerte: /docs/seo/OFFERTE-SEO-bertvanderheide.md (pas aan)
4. Stuur email: /docs/business/EMAIL-TEMPLATES-MIGRATIE.md
```

### "Ik heb een vraag over het Bert project"
```
1. Lees: /projecten/bert-van-der-heide/README.md
2. Voor details:
   - Offerte: /projecten/bert-van-der-heide/documentatie/offerte-bert.md
   - SEO analyse: /docs/seo/SEO-AUDIT-bertvanderheide.md
   - Intake: /projecten/bert-van-der-heide/documentatie/intake-checklist.md
```

### "Hoe werkt de VPS server?"
```
1. Lees: /docs/technisch/README.md
2. Details: /docs/technisch/VPS-GEGEVENS-OVERZICHT.md
```

### "Waarom kan ik site niet gewoon downloaden?"
```
Lees: /docs/technisch/WAAROM-SCRAPING-NIET-WERKT.md
(Uitleg: database vs HTML, waarom toegang nodig)
```

---

## 📊 Bestand Typen & Functie

### 📄 README.md Bestanden (7 totaal)
```
/ README.md                                → Hoofdoverzicht (START)
/docs/README.md                            → Docs categorie overzicht
/docs/technisch/README.md                  → Technische docs index
/docs/business/README.md                   → Business docs index
/docs/seo/README.md                        → SEO docs index
/projecten/README.md                       → Projecten overzicht
/projecten/bert-van-der-heide/README.md    → Project Bert overzicht
```

**→ Altijd README eerst lezen voor context!**

### 📄 Detail Documentatie (14 totaal)
```
Technisch (6):
- VPS-GEGEVENS-OVERZICHT.md
- WEBHOSTING-NIEUWE-SITE.md
- SITE-MIGRATIE-METHODEN.md
- DOWNLOAD-TOOLS-VERGELIJKING.md
- FILAMENT-WORKFLOW-BERT.md (Laravel + Filament admin)
- WAAROM-SCRAPING-NIET-WERKT.md

Business (1):
- EMAIL-TEMPLATES-MIGRATIE.md

SEO (3):
- SEO-AUDIT-bertvanderheide.md
- OFFERTE-SEO-bertvanderheide.md
- GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md

Project Bert (4):
- Hosten op havun.md
- offerte-bert.md
- intake-checklist.md
- home-content.html
```

---

## 🎨 Kleurcode (Voor Snelle Herkenning)

```
🔧 Technisch (groen)    - Server, migratie, tools
💼 Business (blauw)     - Templates, processen, workflows
📈 SEO (paars)          - Audits, strategieën, rankings
🎯 Project (oranje)     - Client specifiek
📋 Overzicht (grijs)    - README's, indices
```

---

## 🚀 Voor Nieuwe Projecten

**Stappen bij nieuwe klant:**

1. Maak map: `/projecten/[clientnaam]/`
2. Kopieer `/projecten/bert-van-der-heide/README.md` als template
3. Kopieer `/projecten/bert-van-der-heide/documentatie/` map
4. Pas aan voor nieuwe klant:
   - README.md (client details)
   - offerte-[naam].md (pricing)
   - intake-checklist.md (gebruik als is)
5. Voeg toe aan `/projecten/README.md` (onder "Actieve Projecten")
6. Update hoofdmenu `/README.md` (sectie "Actieve Projecten")

---

## 📏 Bestand Groottes (Schatting)

```
Klein (<100 regels):
- Alle README.md bestanden
- STRUCTURE.md
- .gitignore

Medium (100-500 regels):
- VPS-GEGEVENS-OVERZICHT.md
- WEBHOSTING-NIEUWE-SITE.md
- SITE-MIGRATIE-METHODEN.md
- DOWNLOAD-TOOLS-VERGELIJKING.md
- GOOGLE-SEARCH-CONSOLE-VERIFICATIE.md
- offerte-bert.md

Groot (500-1000 regels):
- WAAROM-SCRAPING-NIET-WERKT.md (~600 regels)
- EMAIL-TEMPLATES-MIGRATIE.md (~670 regels)
- OFFERTE-SEO-bertvanderheide.md (~710 regels)
- intake-checklist.md (~475 regels)

Zeer Groot (1000+ regels):
- SEO-AUDIT-bertvanderheide.md (~1.256 regels, 12.000+ woorden!)
- Hosten op havun.md (~456 regels, project braindump)
```

**→ Lees grote bestanden alleen als echt nodig!**

---

## 🔐 Gevoelige Informatie (NIET in Git)

**Let op: Deze info NIET committen:**

```
❌ SSH private keys
❌ Database wachtwoorden
❌ WordPress admin credentials
❌ FTP/SFTP toegang
❌ Email wachtwoorden
❌ Google Analytics/Search Console logins
❌ Client contactgegevens (telefoon, privé email)
❌ Database dumps (.sql)
❌ Backup files (.zip, .tar.gz)
```

**→ Zie `.gitignore` voor complete lijst**

**✅ WEL in Git:**
- Alle documentatie (MD files)
- Templates (generiek, geen specifieke credentials)
- Workflows en processen
- Code snippets (zonder wachtwoorden)

---

## 📅 Versie Geschiedenis

**Versie 2.0** (23 november 2025)
- ✅ Hiërarchische structuur geïmplementeerd
- ✅ 7 README.md bestanden toegevoegd (navigatie)
- ✅ Bestanden gecategoriseerd (technisch/business/seo/projecten)
- ✅ STRUCTURE.md toegevoegd (deze file)
- ✅ .gitignore toegevoegd (security)

**Versie 1.0** (9-22 november 2025)
- ✅ Alle documentatie geschreven
- ✅ SEO audit voltooid (12.000+ woorden)
- ✅ Offertes gemaakt (hosting + SEO)
- ✅ Email templates (10 stuks)
- ✅ Technische docs compleet

---

## 💡 Tips voor Claude

### Context Management
```
✅ Start altijd met README.md (overzicht)
✅ Navigeer naar specifieke categorie
✅ Lees alleen detail file als nodig
✅ Gebruik CTRL+F om te zoeken binnen file
✅ Verwijs naar andere docs met relatieve links

❌ Lees NIET alle files in één keer
❌ Ga NIET blind door alle docs
❌ Veronderstel NIET dat je alles moet lezen
```

### Vragen Beantwoorden
```
Vraag: "Hoe voeg ik nieuwe site toe?"
→ Verwijs naar: /docs/technisch/WEBHOSTING-NIEUWE-SITE.md

Vraag: "Hoe vraag ik toegang aan bij klant?"
→ Verwijs naar: /docs/business/EMAIL-TEMPLATES-MIGRATIE.md

Vraag: "Wat is de status van Bert project?"
→ Lees: /projecten/bert-van-der-heide/README.md

Vraag: "Hoe doe ik SEO audit?"
→ Verwijs naar: /docs/seo/SEO-AUDIT-bertvanderheide.md
```

---

## 🔗 Externe Resources

**Documentatie:**
- [Hetzner Docs](https://docs.hetzner.com/)
- [Apache 2.4 Docs](https://httpd.apache.org/docs/2.4/)
- [WordPress Codex](https://codex.wordpress.org/)
- [Google Search Central](https://developers.google.com/search)

**Tools:**
- [PageSpeed Insights](https://pagespeed.web.dev/)
- [SSL Labs](https://www.ssllabs.com/ssltest/)
- [What's My DNS](https://www.whatsmydns.net/)
- [Schema.org Validator](https://validator.schema.org/)

---

**📅 Laatst bijgewerkt:** 23 november 2025
**✍️ Auteur:** Henk - Havun Web Services
**📧 Contact:** havun22@gmail.com

[← Terug naar Hoofdmenu](README.md)

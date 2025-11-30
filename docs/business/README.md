# 💼 Business Documentatie

> **Templates, processen en workflows voor klantcommunicatie**

---

## 📋 Documenten

### [EMAIL-TEMPLATES-MIGRATIE.md](EMAIL-TEMPLATES-MIGRATIE.md)
**Wat:** 10 professionele email templates voor het complete migratie proces
**Gebruik:** Copy-paste en personaliseer per klant
**Inhoud:**

#### Migratie Proces Templates
1. **Eerste Contact** - Welkom na offerte akkoord
2. **Toegang Aanvragen** - 3 opties uitleggen (WordPress/FTP/Backup)
3. **WordPress Specifiek** - Admin login instructies
4. **FTP/cPanel Specifiek** - Technische gegevens aanvragen
5. **Backup Request** - Template voor klant naar huidige host
6. **Herinneringsmail** - Vriendelijke reminder na 3 dagen

#### Post-Migratie Templates
7. **Na Migratie** - Nieuwe login gegevens overdragen
8. **DNS Switch Aankondiging** - Planning go-live moment
9. **DNS Instructies** - Stap-voor-stap voor klant
10. **Afsluiting** - Oude hosting opzeggen

---

## 🎯 Gebruik Per Fase

### Fase 1: Onboarding (Na Offerte Akkoord)
```
Dag 1: Template #1 - Eerste Contact
  ↓
Dag 2: Template #2 - Toegang Aanvragen (3 opties)
  ↓
Klant kiest optie:
  ├─ WordPress → Template #3
  ├─ FTP/cPanel → Template #4
  └─ Backup → Template #5
  ↓
Geen reactie na 3 dagen?
  └─ Template #6 - Herinneringsmail
```

### Fase 2: Migratie Voltooid
```
Testing OK:
  ↓
Template #7 - Nieuwe Login Gegevens
  ↓
Klant test en geeft akkoord:
  ↓
Template #8 - DNS Switch Aankondiging
  ↓
Klant kiest:
  ├─ Zelf DNS wijzigen → Template #9
  └─ Jij doet DNS → Toegang vragen
  ↓
2 weken na go-live:
  └─ Template #10 - Oude hosting opzeggen
```

---

## 💡 Tips Voor Gebruik

### Personaliseren
```
Vervang overal:
[Naam] → Voornaam klant
[sitenaam] → Bedrijfsnaam
[jouwsite] → example.nl
[Oude Host] → Naam huidige provider
[Je nummer] → Jouw telefoonnummer
```

### Tone of Voice
✅ Professioneel maar toegankelijk
✅ Technische termen uitleggen
✅ Geruststellen over security
✅ Duidelijke stappen aangeven
✅ Bereikbaar blijven voor vragen

### Timing
- Stuur templates niet allemaal tegelijk
- Geef klant 2-3 dagen om te reageren
- Stuur herinneringsmail na 3-4 dagen
- Wees geduldig maar proactief

---

## 📞 Standaard Handtekening

Voeg toe aan alle emails:

```
---
Henk
Havun Web Services
Email: havun22@gmail.com
Telefoon: [Je nummer]
```

---

## 🚨 Belangrijke Punten

### Altijd Vermelden:
✓ Waarom toegang nodig is (complete migratie, niet alleen HTML)
✓ Eenmalig gebruik (na migratie geen toegang meer nodig)
✓ Security (nieuwe wachtwoorden, geen opslag oude credentials)
✓ Opties (altijd meerdere keuzes geven)

### Nooit Doen:
✗ Technische jargon zonder uitleg
✗ Druk uitoefenen ("URGENT!", "NU NODIG!")
✗ Vragen om wachtwoorden per telefoon
✗ Meerdere mails per dag

---

## 📋 Checklist Per Klant

```
□ Template #1 verstuurd (Eerste contact)
□ Template #2 verstuurd (Toegang opties)
□ Klant heeft gekozen: □ WP □ FTP □ Backup
□ Specifieke instructies verstuurd (#3/#4/#5)
□ Toegang ontvangen op: _____
□ Migratie voltooid op: _____
□ Template #7 verstuurd (Nieuwe login)
□ Klant heeft getest: □ Ja □ Nee
□ DNS switch gepland op: _____
□ Template #8 verstuurd (DNS aankondiging)
□ DNS gewijzigd door: □ Klant □ Jou
□ Site live sinds: _____
□ Template #10 verstuurd (Opzegging oude host)
```

---

## 🔗 Gerelateerde Docs

**Voor technische migratie:**
→ [../technisch/SITE-MIGRATIE-METHODEN.md](../technisch/SITE-MIGRATIE-METHODEN.md)

**Voor uitleg waarom toegang nodig:**
→ [../technisch/WAAROM-SCRAPING-NIET-WERKT.md](../technisch/WAAROM-SCRAPING-NIET-WERKT.md)

**Voor project specifieke offerte:**
→ [../../projecten/bert-van-der-heide/documentatie/offerte-bert.md](../../projecten/bert-van-der-heide/documentatie/offerte-bert.md)

---

[← Terug naar Docs](../README.md) | [← Terug naar Hoofdmenu](../../README.md)

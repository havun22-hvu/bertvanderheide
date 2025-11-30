# SEO Audit - bertvanderheide.nl

**Datum Analyse:** 22 november 2025
**Geanalyseerde URL:** https://bertvanderheide.nl
**Doelgroep:** Nabestaanden in Enschede en omgeving
**Primaire Keywords:** uitvaartondernemer enschede, crematie hengelo, uitvaart twente

---

## 📊 Executive Summary

### Huidige Status: 6/10 (oude WordPress site)

**Positief (huidige site):**
- ✅ Google Analytics actief
- ✅ SSL/HTTPS certificaat
- ✅ Schema.org markup aanwezig
- ✅ Responsive design

**Kritieke Verbeterpunten:**
- ❌ Title tag te generiek, mist lokale keywords
- ❌ Schema.org niet geoptimaliseerd voor FuneralHome
- ❌ Google My Business niet geclaimd/geoptimaliseerd
- ❌ H1 tag niet keyword-rijk
- ❌ Geen blog/content marketing strategie zichtbaar
- ❌ Technische SEO verbeteringen nodig

**Onze Oplossing:**
→ Nieuwe maatwerk site met Laravel + Filament
→ Claude verzorgt ALLE SEO automatisch
→ Geen WordPress/Yoast nodig!

---

## 🔍 DEEL 1: Technische SEO Analyse

### 1.1 Huidige Technische Setup (Oude Site - Wordt Vervangen!)

```
HUIDIGE SITE (bij Mooi Online):
CMS: WordPress 6.8.3
SEO Plugin: Yoast SEO 26.4
Server: LiteSpeed
Hosting: Mooi Online (IP: 84.247.13.197)
SSL: ✅ Actief (HTTPS)
Caching: WP Rocket 3.20.1.2
Theme: Total + Child Theme (commercieel - licentie issues!)
Analytics: Google Analytics (G-V0KDW6CVRG)

NIEUWE SITE (onze aanpak):
CMS: Laravel 11 + Filament 3 (maatwerk!)
SEO: Claude AI (automatisch, geen plugins)
Server: Nginx op Hetzner VPS
Hosting: Havun Web Services (188.245.159.115)
SSL: Let's Encrypt (gratis, automatisch)
CSS: Tailwind CSS
Database: MySQL 8.x
```

### 1.2 Title Tag Analyse ❌ KRITIEK

**Huidig:**
```html
<title>Bert van der Heide Uitvaartzorg</title>
```

**Problemen:**
- Geen lokale keywords (Enschede, Twente)
- Geen dienst keywords (uitvaart, crematie, begrafenis)
- Te kort (29 karakters, optimaal is 50-60)
- Mist call-to-action element

**Aanbevolen:**
```html
<title>Uitvaartondernemer Enschede | Bert van der Heide Uitvaartzorg</title>
```
Of:
```html
<title>Uitvaart Enschede - Crematie & Begrafenis | Bert van der Heide</title>
```

**Impact:** ⭐⭐⭐⭐⭐ (Zeer hoog - dit is de belangrijkste SEO factor!)

**Onze implementatie:** Claude bouwt dit direct in de Laravel blade templates

---

### 1.3 Meta Description ✅ GOED

**Huidig:**
```html
<meta name="description" content="Bert van der Heide Uitvaartzorg.
Wij verzorgen op een persoonlijke wijze crematies en begrafenissen
in Enschede en omgeving." />
```

**Analyse:**
- ✅ Bevat locatie (Enschede)
- ✅ Bevat diensten (crematies, begrafenissen)
- ✅ Goede lengte (119 karakters, optimaal 150-160)
- ⚠️ Kan sterker met USP

**Verbeterde versie:**
```html
Uitvaartondernemer in Enschede ✓ 24/7 bereikbaar ✓ Persoonlijke begeleiding
bij crematie en begrafenis ✓ Ook Hengelo, Almelo & omgeving ✓ Direct contact
```

**Impact:** ⭐⭐⭐ (Medium - goed maar kan beter)

---

### 1.4 Heading Structure (H1-H6) ⚠️ VERBETEREN

**Huidige H1:**
```html
<h1>Voor een waardevol afscheid</h1>
```

**Problemen:**
- Geen keywords
- Te algemeen/emotioneel
- Mist lokale focus

**Aanbevolen H1 opties:**
```html
Optie 1: <h1>Uitvaartondernemer Enschede - Persoonlijke Uitvaartzorg</h1>
Optie 2: <h1>Crematie en Begrafenis in Enschede | Bert van der Heide</h1>
Optie 3: <h1>Uitvaartzorg Enschede: 24/7 Bereikbaar voor Nabestaanden</h1>
```

**Huidige H2-H6 structuur:**
```
H2: Aanwezig maar niet geanalyseerd in scrape
H3-H6: Te controleren in volledige site audit
```

**Actie:** Volledige heading audit nodig voor alle pagina's

**Impact:** ⭐⭐⭐⭐ (Hoog)

---

### 1.5 Schema.org Markup ⚠️ VERBETEREN

**Huidig Schema Type: Organization**
```json
{
  "@type": "Organization",
  "name": "Bert van der Heide Uitvaartzorg",
  "url": "https://bertvanderheide.nl/",
  "logo": "...",
  "address": {
    "streetAddress": "Livingstonestraat 44",
    "addressLocality": "Enschede",
    "postalCode": "7532CJ"
  },
  "contactPoint": {
    "telephone": "06 81 02 60 62",
    "email": "info@bertvanderheide.nl"
  }
}
```

**Problemen:**
- ❌ Type "Organization" is te generiek
- ❌ Moet "FuneralHome" type zijn (specifiek voor uitvaartondernemers!)
- ❌ Mist `areaServed` (service gebieden)
- ❌ Mist `priceRange`
- ❌ Mist `openingHours` (24/7)
- ❌ Geen `geo` coordinates

**Aanbevolen Schema (FuneralHome):**
```json
{
  "@context": "https://schema.org",
  "@type": "FuneralHome",
  "name": "Bert van der Heide Uitvaartzorg",
  "image": "https://bertvanderheide.nl/wp-content/uploads/2022/12/logo.png",
  "address": {
    "@type": "PostalAddress",
    "streetAddress": "Livingstonestraat 44",
    "addressLocality": "Enschede",
    "addressRegion": "Overijssel",
    "postalCode": "7532CJ",
    "addressCountry": "NL"
  },
  "geo": {
    "@type": "GeoCoordinates",
    "latitude": 52.2215,
    "longitude": 6.8937
  },
  "url": "https://bertvanderheide.nl",
  "telephone": "06 81 02 60 62",
  "email": "info@bertvanderheide.nl",
  "priceRange": "€€",
  "openingHoursSpecification": {
    "@type": "OpeningHoursSpecification",
    "dayOfWeek": [
      "Monday", "Tuesday", "Wednesday", "Thursday",
      "Friday", "Saturday", "Sunday"
    ],
    "opens": "00:00",
    "closes": "23:59"
  },
  "areaServed": [
    {
      "@type": "City",
      "name": "Enschede"
    },
    {
      "@type": "City",
      "name": "Hengelo"
    },
    {
      "@type": "City",
      "name": "Almelo"
    },
    {
      "@type": "City",
      "name": "Oldenzaal"
    }
  ],
  "hasOfferCatalog": {
    "@type": "OfferCatalog",
    "name": "Uitvaartdiensten",
    "itemListElement": [
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Crematie",
          "description": "Volledige begeleiding bij crematie"
        }
      },
      {
        "@type": "Offer",
        "itemOffered": {
          "@type": "Service",
          "name": "Begrafenis",
          "description": "Persoonlijke begrafenisdiensten"
        }
      }
    ]
  }
}
```

**Impact:** ⭐⭐⭐⭐⭐ (Zeer hoog - direct effect op rich snippets!)

---

### 1.6 XML Sitemap ⚠️ TE CONTROLEREN

**Te checken:**
```
https://bertvanderheide.nl/sitemap_index.xml
https://bertvanderheide.nl/sitemap.xml
```

**Yoast SEO genereert automatisch sitemaps, maar:**
- [ ] Controleren of sitemap bestaat
- [ ] Controleren of alle belangrijke pagina's erin staan
- [ ] Controleren of sitemap ingediend is bij Google Search Console

**Actie:** Sitemap URL checken en indien nodig aanmaken/indienen

---

### 1.7 Robots.txt ⚠️ TE CONTROLEREN

**Te checken:**
```
https://bertvanderheide.nl/robots.txt
```

**Moet bevatten:**
```
User-agent: *
Allow: /

Sitemap: https://bertvanderheide.nl/sitemap_index.xml
```

---

### 1.8 Page Speed ⚠️ WAARSCHIJNLIJK GOED

**Positief:**
- ✅ WP Rocket caching plugin actief
- ✅ Image lazy loading (data-rocket-lazyload)
- ✅ Font preloading
- ✅ DNS prefetching

**Te testen:**
- [ ] PageSpeed Insights score
- [ ] Core Web Vitals (LCP, FID, CLS)
- [ ] Mobile usability

**Tools te gebruiken:**
```
https://pagespeed.web.dev/
GTmetrix.com
```

---

### 1.9 Mobile Friendliness ✅ GOED

```html
<meta name="viewport" content="width=device-width, initial-scale=1">
```

**Responsive theme actief:** Total theme met mobile menu

**Te testen:**
- [ ] Google Mobile-Friendly Test
- [ ] Alle pagina's op mobile testen

---

### 1.10 SSL/HTTPS ⚠️ CERTIFICAAT PROBLEEM

**Status:** HTTPS actief, maar:
```
curl error: CRYPT_E_NO_REVOCATION_CHECK
```

**Mogelijke problemen:**
- Certificaat revocation check issues
- Mogelijk tussentijds certificaat probleem

**Actie:**
- [ ] SSL certificaat testen op: https://www.ssllabs.com/ssltest/
- [ ] Controleren of alle resources via HTTPS laden (mixed content)

---

## 🔍 DEEL 2: On-Page SEO Analyse

### 2.1 Homepage Content Analyse

**H1 Tag:** "Voor een waardevol afscheid"
- ❌ Geen keywords
- ❌ Te emotioneel, niet informatief

**Intro Content:**
```
"Bert en Koen van der Heide Uitvaartzorg is een uitvaartonderneming
in Enschede, gespecialiseerd in persoonlijke en respectvolle
Uitvaartzorg in Enschede, Hengelo en rondom."
```

**Positief:**
- ✅ Bevat "uitvaartonderneming in Enschede"
- ✅ Bevat "Hengelo"
- ✅ Bevat "persoonlijke" (USP)

**Negatief:**
- ⚠️ Keyword "Enschede" herhaald (kan naturaler)
- ⚠️ Mist "crematie", "begrafenis" in opening
- ⚠️ Mist "24/7 bereikbaar" (sterke USP)

**Verbeterde versie:**
```
Bert en Koen van der Heide Uitvaartzorg is een zelfstandige
uitvaartonderneming in Enschede. Wij begeleiden families bij
crematie en begrafenis in Enschede, Hengelo, Almelo en omgeving.
24 uur per dag bereikbaar voor persoonlijke en respectvolle uitvaartzorg.
```

---

### 2.2 Keyword Density Analyse

**Primaire Keywords:**
- "uitvaart" / "uitvaartzorg" - ✅ Aanwezig
- "crematie" - ✅ Aanwezig
- "begrafenis" - ✅ Aanwezig
- "Enschede" - ✅ Aanwezig
- "Hengelo" - ⚠️ 1x genoemd (te weinig)
- "Almelo" - ⚠️ Mogelijk niet genoemd
- "24/7" / "dag en nacht" - ⚠️ Te controleren

**Long-tail keywords (MISSEN):**
- "uitvaartondernemer enschede"
- "wat kost een uitvaart"
- "uitvaart regelen"
- "persoonlijke uitvaart"
- "begrafenis kosten"
- "crematie kosten"

**Actie:** Content aanvullen met long-tail keywords

---

### 2.3 Internal Linking ⚠️ TE ANALYSEREN

**Menu items gevonden:**
```
- Home
- Overlijden
- Uitvaart
- Wie zijn wij
- Samenwerkingen
- Contact
```

**Te controleren:**
- [ ] Zijn er interne links vanuit content?
- [ ] Link alle subpagina's terug naar homepage?
- [ ] Zijn anchor texts geoptimaliseerd?
- [ ] Is er een blog met internal linking?

---

### 2.4 Image Optimization ⚠️ TE VERBETEREN

**Logo image:**
```html
<img src="https://bertvanderheide.nl/wp-content/uploads/2022/12/logo.png"
     alt="Bert van der Heide"
     width="400">
```

**Alt-text:**
- ✅ Alt text aanwezig
- ⚠️ Maar: "Bert van der Heide" mist keywords

**Aanbevolen:**
```html
alt="Bert van der Heide Uitvaartzorg Enschede - Logo"
```

**Actie:**
- [ ] Alle afbeeldingen controleren op alt-tags
- [ ] Alt-tags optimaliseren met keywords (niet overdrijven!)
- [ ] Bestandsnamen optimaliseren (bijv. uitvaart-enschede.jpg)

---

### 2.5 URL Structure ✅ GOED

**Homepage:** `https://bertvanderheide.nl/`

**Subpagina's (vermoedelijk):**
```
/overlijden/          ✅ Clean URL
/uitvaart/            ✅ Clean URL
/wie-zijn-wij/        ✅ Clean URL
/samenwerkingen/      ✅ Clean URL
/contact/             ✅ Clean URL
```

**Aanbevelingen:**
- ✅ URLs zijn clean (geen ?p=123)
- ✅ URLs bevatten keywords
- ⚠️ Check of alle URLs HTTPS zijn (geen mixed content)

---

## 🔍 DEEL 3: Off-Page SEO Analyse

### 3.1 Google My Business ❌ KRITIEK!

**Status:** Niet geverifieerd in HTML
- Geen Google verification tag gevonden
- Geen GMB link in schema markup

**Te controleren:**
```
Google Maps: "Bert van der Heide Uitvaartzorg Enschede"
```

**Acties:**
1. [ ] Check of GMB profiel bestaat
2. [ ] Indien niet: Aanmaken en claimen
3. [ ] Indien wel: Optimaliseren (zie sectie 5)

**Impact:** ⭐⭐⭐⭐⭐ (Zeer hoog - 40% van lokaal SEO succes!)

---

### 3.2 Backlinks ⚠️ ONBEKEND

**Te analyseren met tools:**
```
- Ahrefs
- Moz Link Explorer
- Google Search Console (Backlinks sectie)
```

**Verwachte situatie:**
- Mogelijk weinig backlinks (kleine lokale speler)
- Mogelijk directory listings (uitvaart directories)

**Kansen:**
- Lokale directories (Twente.com, etc)
- Branche directories (uitvaartgids.nl)
- Partnerships (bloemisten, aula's, etc)

---

### 3.3 Social Media Presence ⚠️ TE CONTROLEREN

**HTML bevat:**
```html
<meta property="og:type" content="website" />
<meta name="twitter:card" content="summary_large_image" />
```

**Open Graph tags aanwezig (goed!)**, maar:
- [ ] Geen social media links gevonden in schema
- [ ] Check of Facebook/LinkedIn actief is

**Actie:**
- [ ] Social media profiles identificeren
- [ ] Links toevoegen aan website footer
- [ ] Social sharing buttons overwegen

---

### 3.4 Local Citations ⚠️ TE BOUWEN

**Wat zijn local citations?**
Vermeldingen van NAP (Name, Address, Phone) op andere websites

**Belangrijke directories voor uitvaart:**
```
- Google My Business (hoogste prioriteit!)
- uitvaart.nl
- uitvaartgids.nl
- Twente.com directories
- Enschede.nl
- Local business directories
```

**NAP Consistency check:**
```
Naam: Bert van der Heide Uitvaartzorg
Adres: Livingstonestraat 44, 7532CJ Enschede
Telefoon: 06 81 02 60 62
Email: info@bertvanderheide.nl
```

**Actie:** NAP moet EXACT hetzelfde zijn op alle platforms!

---

## 🔍 DEEL 4: Content Marketing Analyse

### 4.1 Blog Status ❌ GEEN BLOG ZICHTBAAR

**Observatie:**
- Geen `/blog/` URL in menu
- Geen recent blog posts op homepage
- Geen RSS feed link prominent

**Gemiste kansen:**
```
Long-tail traffic via blog posts zoals:
- "Wat kost een uitvaart in Enschede?"
- "Checklist na overlijden"
- "Crematie vs begrafenis: wat zijn de verschillen?"
- "Hoe kies je een uitvaartondernemer?"
- "Uitvaartverzekering: wat dekt het?"
```

**Impact van blog:**
- +200-500 bezoekers/maand mogelijk
- Long-tail keyword rankings
- Authority building
- Internal linking mogelijkheden

**Aanbeveling:** Blog starten (zie actieplan)

---

### 4.2 Existing Content Audit

**Bestaande pagina's:**
```
1. Home (/)
2. Overlijden (/overlijden/)
3. Uitvaart (/uitvaart/)
4. Wie zijn wij (/wie-zijn-wij/)
5. Samenwerkingen (/samenwerkingen/)
6. Contact (/contact/)
```

**Per pagina analyseren:**
- [ ] Title tag optimalisatie
- [ ] Meta description
- [ ] H1-H6 structuur
- [ ] Keyword focus
- [ ] Content lengte (min 300 woorden)
- [ ] Internal links
- [ ] Call-to-actions

**Actie:** Volledige content audit van alle 6 pagina's

---

### 4.3 Content Gaps Analyse

**Missende belangrijke pagina's:**
```
1. FAQ pagina (veel SEO waarde!)
   - "Hoeveel kost een uitvaart?"
   - "Hoe snel moet een uitvaart geregeld?"
   - "Wat te doen bij overlijden?"

2. Diensten detail pagina's:
   - Crematie (apart)
   - Begrafenis (apart)
   - Persoonlijke uitvaart

3. Service areas pagina's:
   - Uitvaart Enschede
   - Uitvaart Hengelo
   - Uitvaart Almelo

4. Kosten/Prijzen pagina
   - "Wat kost een uitvaart" → SEO goud!

5. Condoleance register (zag ik in HTML snippet)
   - Goed! Maar promoten voor engagement
```

**Impact:** ⭐⭐⭐⭐ (Hoog - meer pagina's = meer rankings)

---

## 🔍 DEEL 5: Google My Business Strategie

### 5.1 GMB Profile Optimization Checklist

**Basis Setup:**
```
□ Profiel geclaimd
□ Bedrijfsnaam exact: "Bert van der Heide Uitvaartzorg"
□ Adres: Livingstonestraat 44, 7532CJ Enschede
□ Telefoon: 06 81 02 60 62
□ Website: https://bertvanderheide.nl
□ Categorie PRIMARY: Funeral Home
□ Categorie SECONDARY: Cremation Service
□ Service areas: Enschede, Hengelo, Almelo, Oldenzaal, Borne, Losser
□ Openingstijden: 24/7 (altijd bereikbaar)
□ Beschrijving (750 karakters max):
  "Bert van der Heide Uitvaartzorg is een zelfstandige,
   kleinschalige uitvaartonderneming in Enschede. Wij begeleiden
   families bij het regelen van een persoonlijke crematie of
   begrafenis in Enschede, Hengelo, Almelo en omgeving.
   24 uur per dag bereikbaar voor noodgevallen. Wij nemen de
   tijd voor uw wensen en verzorgen alles van A tot Z: van
   eerste gesprek tot dag van afscheid. Eerlijk, betrokken
   en zonder haast. Neem contact op voor meer informatie."
```

**Foto's (minimum 10-15):**
```
□ Exterior foto (gebouw voorkant)
□ Interior foto's (aula, ontvangstruimte)
□ Team foto's (Bert & Koen)
□ Logo (high-res)
□ Service voorbeelden (met toestemming!)
□ 360° tour (optioneel maar impact!)
```

**Attributen:**
```
□ "Rolstoeltoegankelijke ingang"
□ "Rolstoeltoegankelijk toilet"
□ "Parkeren beschikbaar"
□ "LGBTQ+-vriendelijk" (indien van toepassing)
```

---

### 5.2 GMB Posts Strategie (40% van lokaal succes!)

**Frequentie:** Wekelijks (4x per maand minimum)

**Post types rotatie:**
```
Week 1: Update
  "Deze week verzorgden we 3 persoonlijke uitvaarten in
   Enschede en Hengelo. Elke uitvaart uniek, zoals het hoort."

Week 2: Offer (informatief, geen verkoop!)
  "Wist je dat een uitvaart volledig personaliseerbaar is?
   Van muziek tot locatie - wij helpen je wensen vorm te geven."

Week 3: Event/News
  "Nieuwe samenwerking met lokale bloemist voor persoonlijke
   bloemstukken. Vraag naar de mogelijkheden."

Week 4: Educational
  "Checklist: Wat te doen bij een overlijden? Download onze
   gratis gids op onze website."
```

**CTA in elke post:**
```
- "Bel ons 24/7: 06 81 02 60 62"
- "Meer info: bertvanderheide.nl"
- "Plan een vrijblijvend gesprek"
```

---

### 5.3 Reviews Strategie

**Current:** Onbekend (check GMB profiel)

**Target:** 10+ reviews, gemiddeld 4.5+ ⭐

**Hoe reviews vragen:**
```
1. Direct na uitvaart (1-2 weken later):
   Email/brief met link naar GMB review pagina

2. Template:
   "Beste [naam],

   We hopen dat de uitvaart van [overledene] is verlopen
   zoals u voor ogen had. Mocht u een moment hebben, dan
   waarderen wij het zeer als u uw ervaring deelt via
   Google. Dit helpt andere families bij het maken van
   een keuze voor hun uitvaart.

   [LINK NAAR GMB REVIEW]

   Hartelijke groet,
   Bert en Koen"
```

**Review response strategie:**
```
- Beantwoord ALLE reviews binnen 24 uur
- Positieve reviews: bedanken, persoonlijk maken
- Negatieve reviews: excuses, oplossing aanbieden, offline verder
```

---

### 5.4 Q&A Sectie Pre-Seeding

**Veelgestelde vragen proactief beantwoorden:**

```
Q: "Wat kost een uitvaart gemiddeld?"
A: "De kosten van een uitvaart variëren per wensen en keuzes.
    Een eenvoudige crematie start vanaf ongeveer €3.500,
    terwijl een volledige begrafenis vanaf €4.500 kan zijn.
    Wij bespreken graag vrijblijvend uw wensen en maken
    een transparant kostenplaatje. Bel ons: 06 81 02 60 62"

Q: "Zijn jullie 24/7 bereikbaar?"
A: "Ja, wij zijn dag en nacht bereikbaar op 06 81 02 60 62.
    Bij overlijden kunt u ons direct bellen, ook in het weekend
    of midden in de nacht."

Q: "Verzorgen jullie ook uitvaarten in Hengelo?"
A: "Ja, naast Enschede verzorgen wij ook uitvaarten in Hengelo,
    Almelo, Oldenzaal en omliggende plaatsen in Twente."

Q: "Hoeveel tijd is er tussen overlijden en uitvaart?"
A: "Gemiddeld is er 7-14 dagen tussen overlijden en de uitvaart.
    Dit geeft tijd voor voorbereidingen en voor familie om te reizen.
    In spoedsituaties kan dit korter, in bijzondere gevallen langer."

Q: "Werken jullie samen met uitvaartverenigingen?"
A: "Ja, wij werken graag samen met uitvaartverenigingen en
    respecteren hun wensen en protocollen."
```

**Voordeel:** Google toont deze Q&A prominent in search results!

---

## 🔍 DEEL 6: Competitor Analysis

### 6.1 Top Concurrenten Enschede

**Te analyseren:**
```
1. [Concurrent 1] - Check rankings, GMB, content
2. [Concurrent 2] - Check rankings, GMB, content
3. [Concurrent 3] - Check rankings, GMB, content
```

**Per concurrent checken:**
- [ ] Google rankings voor "uitvaartondernemer enschede"
- [ ] GMB review count & rating
- [ ] Website SEO (Title, content, blog)
- [ ] Backlink profile
- [ ] Wat doen zij goed? (leren van)
- [ ] Wat doen zij slecht? (kans voor ons)

---

## 📋 DEEL 7: Prioritized Action Plan

### FASE 1: Quick Wins (Week 1-2) 🚀

**Impact: Zeer Hoog, Effort: Laag**

#### 1. Title Tag Fix ⭐⭐⭐⭐⭐
```
Huidig: "Bert van der Heide Uitvaartzorg"
Nieuw: "Uitvaartondernemer Enschede | Bert van der Heide Uitvaartzorg"

Hoe: Claude bouwt dit in Laravel blade layout
Tijd: Direct bij site bouw
Impact: Direct ranking boost voor "uitvaartondernemer enschede"
```

#### 2. H1 Tag Optimalisatie ⭐⭐⭐⭐
```
Huidig: "Voor een waardevol afscheid"
Nieuw: "Uitvaartondernemer Enschede - Persoonlijke Uitvaartzorg"

Hoe: Claude bouwt dit in homepage template
Tijd: Direct bij site bouw
Impact: Betere keyword relevantie
```

#### 3. Schema.org FuneralHome Type ⭐⭐⭐⭐⭐
```
Schema type: FuneralHome (niet Organization!)
Service areas: Enschede, Hengelo, Almelo, etc
Opening hours: 24/7

Hoe: Claude genereert JSON-LD in Laravel layout
Tijd: Direct bij site bouw
Impact: Rich snippets, betere visibility
```

#### 4. Google My Business Claimen ⭐⭐⭐⭐⭐
```
Google My Business aanmaken/claimen
Profiel volledig invullen
5-10 foto's uploaden
Service areas instellen
Q&A pre-seeden (5 vragen)

Tijd: 2 uur
Impact: Lokale visibility boost +300%
```

#### 5. Google Search Console Setup ⭐⭐⭐⭐
```
Account aanmaken (als nog niet gedaan)
Sitemap indienen
Eerste data verzamelen

Tijd: 30 minuten
Impact: Inzicht in huidige rankings + issues
```

---

### FASE 2: Medium Term (Week 3-8) 📈

**Impact: Hoog, Effort: Medium**

#### 6. Content Optimalisatie Alle Pagina's ⭐⭐⭐⭐
```
Per pagina (Claude bouwt direct goed!):
- Title tag geoptimaliseerd
- Meta description met keywords
- H1-H6 structuur correct
- Keyword density goed
- Internal links aanwezig
- CTA's op elke pagina

Pagina's (8-10 totaal):
1. Home
2. Over ons / Team
3. Diensten
4. Begrafenis
5. Crematie
6. Kosten / Tarieven
7. FAQ
8. Blog
9. Contact
10. Privacy

Tijd: Inbegrepen bij site bouw door Claude
Impact: Rankings voor alle target pages
```

#### 7. FAQ Pagina Aanmaken ⭐⭐⭐⭐⭐
```
Nieuwe pagina: /veelgestelde-vragen/
Inhoud: 15-20 vragen met antwoorden
Schema markup: FAQPage type

Vragen (SEO goud!):
- Hoeveel kost een uitvaart in Enschede?
- Wat te doen bij overlijden?
- Hoe lang duurt een uitvaart?
- Crematie of begrafenis: wat zijn de verschillen?
- Zijn jullie 24/7 bereikbaar?
- Werken jullie met uitvaartverenigingen?
- etc.

Tijd: 4 uur
Impact: Long-tail keyword rankings + featured snippets
```

#### 8. Blog Starten (6-8 Foundational Posts) ⭐⭐⭐⭐
```
Blog ingebouwd in Laravel + Filament admin

Posts (400-600 woorden elk, door Claude):
1. "Wat kost een uitvaart in Enschede?" (SEO killer!)
2. "Checklist: wat te doen bij overlijden in Twente"
3. "Crematie vs Begrafenis: kosten en verschillen"
4. "Hoe kies je een uitvaartondernemer in Hengelo?"
5. "Uitvaartverzekering: wat dekt het wel/niet?"
6. "Persoonlijke uitvaart: ideeën en voorbeelden"
7. "Dag en nacht bereikbaar: hoe werkt dat?"
8. "Uitvaart regelen zonder uitvaartvereniging"

Tijd: Claude schrijft alle posts
Bert: Checkt en publiceert via Filament admin
Impact: +200-500 bezoekers/maand na 3-6 maanden
```

#### 9. Image SEO Optimization ⭐⭐⭐
```
Alle afbeeldingen:
- Alt-tags optimaliseren met keywords
- Bestandsnamen herschrijven (uitvaart-enschede.jpg)
- Compressie (TinyPNG)
- Lazy loading check

Tijd: 3 uur
Impact: Image search rankings + page speed
```

#### 10. GMB Weekly Posts (Start Routine) ⭐⭐⭐⭐
```
Elke week 1 GMB post
4 posts per maand minimum
Template maken voor efficiency

Tijd: 30 min/week
Impact: GMB ranking boost + engagement
```

---

### FASE 3: Long Term (Maand 3-12) 🎯

**Impact: Zeer Hoog, Effort: Hoog (Ongoing)**

#### 11. Content Marketing (Monthly Blog) ⭐⭐⭐⭐
```
1 blog post per maand (ongoing)
Focus op long-tail keywords
AI-assisted maar handmatig gecontroleerd

Tijd: 2 uur/maand
Impact: Cumulative traffic growth
```

#### 12. Backlink Building ⭐⭐⭐
```
Activiteiten:
- Local directory listings (10-15)
- Partnership links (bloemisten, aula's)
- Guest posts (lokale nieuws sites?)
- HARO (Help A Reporter Out) voor media mentions

Tijd: 2-3 uur/maand
Impact: Domain authority + referral traffic
```

#### 13. GMB Review Generation ⭐⭐⭐⭐
```
Systeem opzetten:
- Na elke uitvaart review vragen (2 weken later)
- Email template
- Follow-up proces

Target: 2-3 reviews per maand
Tijd: 1 uur setup, 30 min/maand maintenance
Impact: Trust + local rankings
```

#### 14. Service Area Pages ⭐⭐⭐⭐
```
Dedicated pages per stad:
- /uitvaart-enschede/
- /uitvaart-hengelo/
- /uitvaart-almelo/
- /uitvaart-oldenzaal/

Elk 300-500 woorden unieke content
Lokale focus (landmarks, bereikbaarheid)

Tijd: 2 uur per pagina = 8 uur
Impact: City-specific rankings
```

#### 15. Technical SEO Monitoring ⭐⭐⭐
```
Maandelijks checken:
- Page speed (PageSpeed Insights)
- Broken links (Screaming Frog)
- Core Web Vitals
- Mobile usability
- SSL status

Tijd: 1 uur/maand
Impact: Maintain rankings, prevent issues
```

---

## 📊 DEEL 8: KPI's & Tracking

### 8.1 Baseline Metrics (Week 1)

**Te meten NU:**
```
Google Search Console:
- [ ] Total clicks (last 3 months)
- [ ] Total impressions
- [ ] Average CTR
- [ ] Average position
- [ ] Top 5 queries

Google Analytics:
- [ ] Monthly visitors
- [ ] Bounce rate
- [ ] Pages per session
- [ ] Avg session duration
- [ ] Top landing pages

Google My Business:
- [ ] Total views
- [ ] Search vs Maps views
- [ ] Actions (calls, website clicks, directions)
- [ ] Review count & rating
```

### 8.2 Success Metrics (Maand 1-3)

**Target Na 3 Maanden:**
```
Organic traffic: +50% (van baseline)
Google rankings:
  - "uitvaartondernemer enschede" → Top 5
  - "crematie hengelo" → Top 10
  - "uitvaart enschede" → Top 3

GMB:
  - Profile views: +200%
  - 5+ nieuwe reviews
  - 10+ foto's
  - 4 posts/maand consistent

Website:
  - 5-10 contactformulier conversies/maand
  - Bounce rate < 60%
```

### 8.3 Long Term Goals (Maand 6-12)

**Target Na 12 Maanden:**
```
Organic traffic: +200-300% (van baseline)
Rankings: Top 3 voor alle primaire keywords
GMB: 10+ reviews, 4.5+ rating
Conversions: 10-15 aanvragen/maand
Blog traffic: 200-500 bezoekers/maand
Backlinks: 20-30 quality links
```

---

## 🔧 DEEL 9: Tools & Resources Nodig

### 9.1 Essential Tools (Gratis)

```
□ Google Search Console (moet!)
□ Google Analytics 4 (moet!)
□ Google My Business (moet!)
□ PageSpeed Insights
□ Mobile-Friendly Test
□ Schema.org Validator
□ SSL Labs

NIET NODIG (Claude doet dit automatisch):
✗ Yoast SEO
✗ RankMath
✗ All in One SEO
✗ Andere WordPress SEO plugins
```

### 9.2 Recommended Tools (Betaald/Freemium)

```
□ Ahrefs / SEMrush (keyword research, backlinks)
  → Freemium: Ubersuggest ($12/maand)

□ Screaming Frog (technical audit)
  → Free versie OK voor kleine site

□ Canva (GMB post graphics)
  → Free versie voldoende

□ TinyPNG (image compression)
  → Free
```

### 9.3 AI Tools (Content Creation)

```
□ Claude / ChatGPT (blog drafts, meta descriptions)
□ Grammarly (proofreading)
□ Hemingway Editor (readability)
```

---

## 📞 DEEL 10: Toegang Nodig

### 10.1 Voor SEO Implementatie

**Website Toegang (NIET nodig bij nieuwe site!):**
```
OUDE SITE (alleen voor content overnemen):
□ WordPress admin login (optioneel)
  URL: https://bertvanderheide.nl/wp-admin/
  User: ?
  Pass: ?

NIEUWE SITE (na bouw door Claude):
□ Filament admin panel
  URL: https://bertvanderheide.nl/admin/
  User: bert@... (wordt aangemaakt)
  Pass: (veilig wachtwoord)
```

**Analytics & Tools:**
```
□ Google Analytics admin toegang
  (of nieuwe GA4 property aanmaken)

□ Google Search Console eigenaar/gebruiker toegang
  (of nieuwe property verifiëren)

□ Google My Business admin toegang
  (of claimen als nog niet gedaan)
```

**Domain/DNS:**
```
□ DNS beheer toegang (voor verification tags)
  Waar geregistreerd: ?
  Login: ?
```

---

## 💰 DEEL 11: Geschatte Tijdsinvestering

### Per Fase:

**FASE 1 (Quick Wins):**
```
Setup: 5-8 uur
Resultaat: Direct zichtbaar (1-4 weken)
```

**FASE 2 (Medium Term):**
```
Setup: 30-40 uur
Resultaat: Zichtbaar na 4-12 weken
```

**FASE 3 (Ongoing):**
```
Maandelijks: 4-6 uur
- 1 blog post (2 uur)
- 4 GMB posts (1 uur)
- Monitoring (1 uur)
- Content updates (1-2 uur)

Resultaat: Cumulatief (groei elke maand)
```

---

## 🎯 DEEL 12: Expected Results Timeline

### Week 1-4 (Quick Wins Fase)
```
✓ Title & H1 fixes live
✓ Schema.org FuneralHome implemented
✓ GMB claimed & optimized
✓ Google Search Console setup
→ Verwacht: Eerste ranking movement
```

### Maand 2-3 (Medium Term Fase)
```
✓ Alle pagina's geoptimaliseerd
✓ FAQ pagina live
✓ 6-8 blog posts live
✓ Weekly GMB posts routine
→ Verwacht: Top 10 rankings primaire keywords
→ Verwacht: +50-100% traffic
```

### Maand 4-6 (Consolidatie)
```
✓ Monthly blog ongoing
✓ Review generation systeem
✓ Backlink building gestart
→ Verwacht: Top 5 rankings
→ Verwacht: +100-200% traffic
→ Verwacht: 5-10 conversies/maand
```

### Maand 7-12 (Mature)
```
✓ Consistent content production
✓ 10+ reviews
✓ 20+ backlinks
✓ Service area pages live
→ Verwacht: Top 3 rankings (meeste keywords)
→ Verwacht: 200-500 bezoekers/maand
→ Verwacht: 10-15 conversies/maand
→ Verwacht: Stabiel lokale marktleider
```

---

## ✅ SAMENVATTING: Top 10 Prioriteiten

### DIRECT STARTEN (Deze Week):

1. **Title Tag Fix** - 5 min, zeer hoog impact ⭐⭐⭐⭐⭐
2. **H1 Tag Optimalisatie** - 5 min, hoog impact ⭐⭐⭐⭐
3. **Schema.org FuneralHome** - 30 min, zeer hoog impact ⭐⭐⭐⭐⭐
4. **Google Search Console** - 30 min, essential ⭐⭐⭐⭐
5. **Google My Business Claim** - 2 uur, zeer hoog impact ⭐⭐⭐⭐⭐

### VOLGENDE 2 WEKEN:

6. **FAQ Pagina** - 4 uur, zeer hoog impact ⭐⭐⭐⭐⭐
7. **Blog Setup + 3 Posts** - 6 uur, hoog impact ⭐⭐⭐⭐
8. **GMB Weekly Posts Start** - 30 min/week, hoog impact ⭐⭐⭐⭐
9. **Content Optimization (6 pagina's)** - 12 uur, hoog impact ⭐⭐⭐⭐
10. **Image SEO** - 3 uur, medium impact ⭐⭐⭐

---

**TOTAAL GESCHATTE TIJD (Eerste Maand):** 30-35 uur

**VERWACHTE RESULTAAT:** Top 10 rankings binnen 6-8 weken voor primaire keywords

---

**Next Steps:**
1. Review deze audit met Bert
2. Toegang regelen (WordPress, GA, GMB)
3. Start met Quick Wins (FASE 1)
4. Plan maandelijkse SEO routine

**Vragen?** Laten we bespreken!

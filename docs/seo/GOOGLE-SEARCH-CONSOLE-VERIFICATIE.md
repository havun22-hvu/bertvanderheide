# Google Search Console Verificatie - bertvanderheide.nl

**Datum:** 22 november 2025
**Status:** Wachten op toegang van Bert

---

## Situatie

Google Search Console vraagt om eigendomsverificatie van **bertvanderheide.nl**.

**Probleem:** De website staat NIET op onze server, maar bij de huidige hosting provider van Bert.

**Extra uitdaging:** Bert weet niets van internet/techniek, dus we moeten dit zelf regelen.

**Huidige provider:** **Mooi Online** (mooionline.nl) - zij hebben de website gebouwd en beheren deze waarschijnlijk.

**IP Adres server:** 84.247.13.197 (LiteSpeed webserver)

---

## PRAKTISCHE AANPAK (aangezien Bert niet technisch is)

### Optie A: Via Huidige Provider (Mooi Online)

**Stap 1:** Vraag Bert om toestemming/volmacht

Email naar Bert:
```
Beste Bert,

Om de SEO werkzaamheden te kunnen starten heb ik toegang nodig tot de website.

Ik zie dat je huidige website is gemaakt door "Mooi Online" (mooionline.nl).

Mag ik namens jou contact met hen opnemen om:
1. Google Search Console verificatie te regelen
2. WordPress admin toegang te krijgen

Dit is nodig om de SEO optimalisaties uit te voeren waar we het over hebben gehad.

Kun je mij daarvoor toestemming geven? Eventueel kan je hen ook een mailtje
sturen dat ik namens jou contact opneem.

Groet,
Henk
```

**Stap 2:** Contact Mooi Online

Email naar info@mooionline.nl:
```
Beste Mooi Online,

Ik ben Henk van Havun Web Services.

In opdracht van jullie klant Bert van der Heide (bertvanderheide.nl) ga ik
de SEO werkzaamheden voor zijn website overnemen.

Om te kunnen starten heb ik het volgende nodig:

1. WordPress admin toegang (editor of administrator role)
   Email: havun22@gmail.com

2. Google Search Console verificatie
   - Optie A: Bijgevoegde HTML tag toevoegen via Yoast SEO
   - Optie B: Bijgevoegd bestand uploaden naar website root

3. Google Analytics toegang (indien aanwezig)

Kunnen jullie dit voor mij regelen? Bert heeft hier toestemming voor gegeven.

Alvast bedankt!

Met vriendelijke groet,
Henk
Havun Web Services
havun22@gmail.com
```

---

### Optie B: WordPress Admin Toegang Direct van Bert

**Als Bert WEL inloggegevens heeft:**

Email naar Bert:
```
Beste Bert,

Voor de SEO werkzaamheden heb ik toegang nodig tot het WordPress
beheerpanel van je website.

Heb jij inloggegevens voor:
https://bertvanderheide.nl/wp-admin/

Zo ja, kun je dan:
1. Een nieuwe gebruiker aanmaken voor mij (havun22@gmail.com)
2. Of mij je huidige inloggegevens sturen (dan maak ik zelf een account aan)

Als je deze gegevens niet hebt, kunnen we contact opnemen met Mooi Online
die je website beheert.

Groet,
Henk
```

---

## Verificatiemethoden (Kies 1)

### ✅ OPTIE 1: HTML Tag Methode (AANBEVOLEN - MAKKELIJKST)

**Voordeel:** Geen FTP toegang nodig, kan via WordPress

**Stappen:**

1. Ga naar Google Search Console → Eigendom verifiëren
2. Klik op **"Html-tag"** tabblad
3. Kopieer de meta tag (ziet er ongeveer zo uit):
   ```html
   <meta name="google-site-verification" content="google01ce0a5b4fd23f31" />
   ```

4. **Stuur naar Bert:**
   ```
   Beste Bert,

   Om Google Search Console in te richten voor SEO analyse heb ik toegang nodig
   tot bertvanderheide.nl.

   Kun je (of je huidige webmaster) deze HTML tag toevoegen aan de <head>
   sectie van je WordPress website?

   <meta name="google-site-verification" content="google01ce0a5b4fd23f31" />

   In WordPress kan dit via:
   - Yoast SEO → General → Webmaster Tools → Google verification code
   - OF via Appearance → Theme Editor → header.php (in <head> sectie)
   - OF via een plugin zoals "Insert Headers and Footers"

   Na toevoeging laat je het even weten, dan kan ik de verificatie afronden.

   Groet,
   Henk
   ```

---

### OPTIE 2: HTML Bestand Upload Methode

**Vereist:** FTP of File Manager toegang

**Stappen:**

1. Download het bestand: **google01ce0a5b4fd23f31.html**
2. Stuur email naar Bert:

   ```
   Beste Bert,

   Bijgevoegd vind je een verificatiebestand voor Google Search Console.

   Kun je dit bestand uploaden naar de root directory van je website?
   (Meestal: /public_html/ of /httpdocs/)

   Het bestand moet daarna bereikbaar zijn via:
   https://bertvanderheide.nl/google01ce0a5b4fd23f31.html

   Dit is nodig om SEO analyse tools in te richten.

   Groet,
   Henk
   ```

---

### OPTIE 3: Google Analytics Methode (ALS JE TOEGANG KRIJGT)

**Vereist:** Google Analytics admin toegang

**Stappen:**

1. Vraag Bert om je toe te voegen als gebruiker in Google Analytics:
   - Analytics → Admin → Account Access Management
   - Add users → havun22@gmail.com → Editor role

2. In Google Search Console:
   - Kies "Google Analytics" als verificatiemethode
   - Search Console detecteert automatisch je GA toegang
   - Verificatie succesvol!

**Email naar Bert:**
```
Beste Bert,

Voor de SEO werkzaamheden heb ik toegang nodig tot je Google Analytics account.

Kun je mij toevoegen als gebruiker?

Stappen:
1. Log in op analytics.google.com
2. Klik op "Admin" (tandwiel icoon linksonder)
3. Onder "Account" → "Account Access Management"
4. Klik "+ Add Users"
5. Voeg toe: havun22@gmail.com
6. Rol: "Editor"
7. Klik "Add"

Dit geeft mij ook automatisch toegang tot Google Search Console voor SEO analyse.

Groet,
Henk
```

---

### OPTIE 4: DNS TXT Record Methode

**Vereist:** Toegang tot domain registrar (DNS beheer)

**Stappen:**

1. Google Search Console → "Domain name provider" methode
2. Kopieer de TXT record waarde
3. Vraag Bert om deze TXT record toe te voegen bij zijn domain registrar

**Email:**
```
Beste Bert,

Voor Google Search Console verificatie kunnen we ook een DNS TXT record toevoegen.

Waar is je domein bertvanderheide.nl geregistreerd?
(Bijvoorbeeld: TransIP, Vimexx, One.com, GoDaddy, etc.)

Ik kan je dan begeleiden bij het toevoegen van de TXT record.

Groet,
Henk
```

---

## Onze Aanbeveling

**Start met OPTIE 1 (HTML Tag)** omdat:
- ✅ Geen FTP toegang nodig
- ✅ Makkelijk via WordPress/Yoast SEO
- ✅ Bert kan het zelf doen (5 minuten)
- ✅ Geen risico op fouten

**Als Optie 1 niet lukt:** Probeer Optie 3 (Google Analytics toegang)

---

## Email Template Voor Bert

**Onderwerp:** Toegang nodig voor SEO opzet - Google Search Console

```
Beste Bert,

Ik ga aan de slag met de SEO voor bertvanderheide.nl zoals besproken.

Om te starten heb ik Google Search Console nodig voor:
- Keyword analyse (welke zoekwoorden brengen bezoekers)
- Ranking monitoring (hoe goed scoren we in Google)
- Technische SEO problemen detecteren

Er zijn twee manieren om dit in te richten:

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

OPTIE A: Jij voegt een HTML tag toe (5 minuten)
→ Makkelijkst, kan via Yoast SEO plugin

OPTIE B: Jij geeft mij Google Analytics toegang
→ Dan kan ik alles zelf regelen

━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

Wat heeft jouw voorkeur?

Voor Optie A stuur ik je de exacte HTML tag die je moet toevoegen.
Voor Optie B voeg je mij toe als gebruiker in Google Analytics.

Laat je het even weten?

Groet,
Henk
```

---

## Wat Na Verificatie?

Zodra Google Search Console geverifieerd is:

1. ✅ Sitemap indienen (`bertvanderheide.nl/sitemap_index.xml`)
2. ✅ Baseline metrics verzamelen (huidige rankings)
3. ✅ URL inspection tool gebruiken voor indexatie check
4. ✅ Performance rapport analyseren (clicks, impressions)
5. ✅ Mobile usability check
6. ✅ Core Web Vitals check

---

## Status Tracking

- [ ] Email gestuurd naar Bert (datum: _____)
- [ ] Methode gekozen: _____
- [ ] Verificatie tag/bestand verstrekt: _____
- [ ] Bert heeft tag toegevoegd: _____
- [ ] Verificatie succesvol: _____
- [ ] Sitemap ingediend: _____
- [ ] Eerste data verzameld: _____

---

**Next:** Zodra verificatie succesvol is, kunnen we starten met de echte SEO werkzaamheden uit de audit!

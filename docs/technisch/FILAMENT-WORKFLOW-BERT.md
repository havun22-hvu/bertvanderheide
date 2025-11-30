# Filament Workflow - Bert van der Heide

> **Hoe Bert en Henk samenwerken met Laravel + Filament**
>
> **Site:** bertvanderheide.nl
> **Staging:** staging.bertvanderheide.nl
> **Admin:** bertvanderheide.nl/admin

---

## Overzicht: Wie doet wat?

| Wie | Waar | Wat |
|-----|------|-----|
| **Henk + Claude** | Staging | Technisch werk, nieuwe features, SEO |
| **Henk** | Production | Content klaarzetten als concept |
| **Bert** | Production Admin | Content checken, aanpassen, publiceren |

---

## Waarom Filament ipv WordPress?

| WordPress | Filament |
|-----------|----------|
| Honderden knoppen | Alleen wat Bert nodig heeft |
| Plugin updates nodig | Geen plugins |
| Verwarrende menu's | Simpel en overzichtelijk |
| Kan site stuk maken | Kan site NIET stuk maken |
| Trage performance | Supersnel |
| Licentie issues thema | 100% eigen code |
| Yoast SEO plugin nodig | Claude doet SEO automatisch |

---

## 3 Niveaus van testen

```
┌─────────────────────────────────────────────────────────────────┐
│ NIVEAU 1: Filament Draft/Preview (ingebouwd)                    │
├─────────────────────────────────────────────────────────────────┤
│ Wat: Pagina/blog opslaan als "concept" → Preview knop           │
│ Wie: Bert kan dit zelf doen                                     │
│ Zichtbaar: Alleen voor ingelogde gebruikers                     │
│ Gebruik: Tekst wijzigingen checken voordat je op "Publiceren"   │
│          klikt                                                  │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│ NIVEAU 2: Staging site (staging.bertvanderheide.nl)             │
├─────────────────────────────────────────────────────────────────┤
│ Wat: Complete kopie van de site op apart subdomein              │
│ Wie: Henk voor grote wijzigingen (code, nieuwe features)        │
│ Zichtbaar: Alleen Henk + Bert (password protected)              │
│ Gebruik: Nieuwe features testen, updates, redesign              │
└─────────────────────────────────────────────────────────────────┘
                              ↓
┌─────────────────────────────────────────────────────────────────┐
│ NIVEAU 3: Production (bertvanderheide.nl)                       │
├─────────────────────────────────────────────────────────────────┤
│ Wat: Live site voor bezoekers                                   │
│ Wie: Bezoekers, Google, iedereen                                │
│ Zichtbaar: Publiek                                              │
└─────────────────────────────────────────────────────────────────┘
```

**Samengevat:**
- **Staging** = voor Henk (technisch werk)
- **Filament Preview** = voor Bert (content op production)

---

## Wat kan Bert in Filament?

### Admin Panel Overzicht

```
┌─────────────────────────────────────────────────────────┐
│  🏠 Dashboard                                            │
├─────────────────────────────────────────────────────────┤
│                                                         │
│  📄 Pagina's                                            │
│     • Home                    [Bewerken]                │
│     • Over ons                [Bewerken]                │
│     • Diensten                [Bewerken]                │
│     • Contact                 [Bewerken]                │
│                                                         │
│  📝 Blog                                                │
│     • Wat kost een uitvaart   [Bewerken]                │
│     • Crematie vs begrafenis  [Bewerken]                │
│     [+ Nieuwe blog]                                     │
│                                                         │
│  ❓ FAQ                                                 │
│     [+ Nieuwe vraag]                                    │
│                                                         │
│  🖼️ Media                                               │
│     [Upload afbeeldingen]                               │
│                                                         │
└─────────────────────────────────────────────────────────┘
```

### Bert kan:
- ✅ Teksten aanpassen (klik → type → opslaan)
- ✅ Nieuwe blogs toevoegen
- ✅ FAQ vragen toevoegen
- ✅ Afbeeldingen uploaden
- ✅ Preview bekijken voor publicatie
- ✅ Concept opslaan (nog niet live)
- ✅ Publiceren wanneer klaar

### Bert hoeft NIET:
- ❌ Plugins updaten (bestaan niet!)
- ❌ Thema instellingen begrijpen (bestaat niet!)
- ❌ Technische dingen doen
- ❌ Bang zijn iets stuk te maken
- ❌ SEO settings invullen (Claude doet dit!)

---

## Content Workflows

### Scenario 1: Henk/Claude maakt content klaar voor Bert

```
Henk's stappen:
1. Claude schrijft tekst
2. Henk logt in op bertvanderheide.nl/admin/
3. Blog → Nieuwe toevoegen
4. Plakt tekst van Claude
5. Klikt "Opslaan als concept" (NIET publiceren!)
6. Stuurt Bert bericht: "Nieuwe tekst klaar om te checken"

Bert's stappen:
1. Logt in op bertvanderheide.nl/admin/
2. Blog → Overzicht
3. Ziet concept staan, klikt erop
4. Leest tekst, past aan waar nodig
5. Klikt "Preview" om te bekijken
6. Tevreden? → Klikt "Publiceren" → Live!
```

### Scenario 2: Bert maakt zelf content

```
Bert's stappen:
1. Logt in op bertvanderheide.nl/admin/
2. Blog → Nieuwe toevoegen
3. Schrijft eigen tekst
4. Klikt "Preview" om te bekijken
5. Tevreden? → Klikt "Publiceren" → Live!
```

### Scenario 3: Bert vraagt Claude om hulp

```
1. Bert vraagt Henk: "Kun je een blog over crematie kosten maken?"
2. Henk vraagt Claude om tekst
3. Claude schrijft complete tekst met SEO
4. Henk zet als concept klaar in Filament
5. Bert checkt en publiceert
```

---

## Claude + Filament Samenwerking

Claude en Filament vullen elkaar aan:

```
┌─────────────────────────────────────┬───────────────────────────────┐
│ CLAUDE                              │ FILAMENT                      │
├─────────────────────────────────────┼───────────────────────────────┤
│ Teksten schrijven                   │ Waar teksten gepubliceerd     │
│ SEO automatisch verwerken           │ worden                        │
│ Blog ideeën bedenken                │                               │
│ Meta descriptions maken             │ Ingebouwd (geen plugin!)      │
│ FAQ content schrijven               │ FAQ beheer                    │
│ Schema.org markup                   │ Ingebouwd in site code        │
│ Technische problemen oplossen       │ Henk voert uit                │
└─────────────────────────────────────┴───────────────────────────────┘
```

**Geen conflict mogelijk** - Claude verzorgt de content & SEO, Filament is waar het resultaat komt.

---

## Praktische Tips voor Bert

### Tekst bewerken

```
1. Login: bertvanderheide.nl/admin/
2. Pagina's → Klik op pagina naam
3. Bewerk tekst in de editor
4. Klik "Preview" rechtsboven
5. Controleer in nieuw tabblad
6. Tevreden? → Klik "Opslaan"
```

### Nieuwe blogpost

```
1. Login: bertvanderheide.nl/admin/
2. Blog → Nieuwe toevoegen
3. Voer titel in
4. Schrijf of plak tekst
5. Uitgelichte afbeelding kiezen (optioneel)
6. Preview → Publiceren
```

### Afbeelding toevoegen

```
1. In de editor: klik op afbeelding icoon
2. Upload nieuwe of kies uit Media bibliotheek
3. Alt-tekst wordt automatisch ingevuld (SEO!)
```

---

## Wanneer Henk inschakelen?

Bert kan Henk vragen bij:

| Situatie | Actie |
|----------|-------|
| Iets werkt niet | Henk checkt |
| Nieuwe feature wens | Henk + Claude bouwen op staging |
| SEO vragen | Henk/Claude - maar meestal automatisch! |
| Technische foutmelding | Henk |
| Nieuw design/layout | Henk + Claude op staging |

---

## Login Gegevens (in te vullen)

### Bert

```
URL: https://bertvanderheide.nl/admin/
Gebruikersnaam: [in te vullen]
Wachtwoord: [in te vullen]
Rol: Editor (kan content beheren, niet site stuk maken)
```

### Henk

```
URL: https://bertvanderheide.nl/admin/
Gebruikersnaam: [in te vullen]
Wachtwoord: [in te vullen]
Rol: Administrator (volledige toegang)
```

---

## SEO - Volledig Automatisch!

### Wat Claude automatisch doet:

| SEO Element | WordPress/Yoast | Onze Laravel Site |
|-------------|-----------------|-------------------|
| Title tags | Handmatig invullen | Automatisch gegenereerd |
| Meta descriptions | Handmatig invullen | Automatisch gegenereerd |
| Schema.org | Plugin nodig | Ingebouwd in code |
| XML Sitemap | Plugin nodig | Automatisch gegenereerd |
| Canonical URLs | Plugin nodig | Automatisch |
| Open Graph | Plugin nodig | Ingebouwd |
| Alt tekst suggesties | Handmatig | Automatisch voorgesteld |

**Bert hoeft NIETS te doen voor SEO!** Claude heeft alles al geregeld bij de bouw.

---

## Verschil met WordPress

### WordPress Admin (verwarrend!)
```
Dashboard
├─ Berichten (blog)
├─ Media
├─ Pagina's
├─ Reacties
├─ Weergave
│   ├─ Thema's
│   ├─ Customizer (???)
│   ├─ Widgets (???)
│   └─ Menu's
├─ Plugins (30 stuks!!)
├─ Gebruikers
├─ Gereedschappen
├─ Instellingen (10+ submenu's)
└─ Yoast SEO
    ├─ Algemeen
    ├─ Zoekweergave
    ├─ Social
    ├─ Sitemaps
    └─ Tools
```

### Filament Admin (simpel!)
```
Dashboard
├─ Pagina's
├─ Blog
├─ FAQ
└─ Media

Dat is alles! 🎉
```

---

**Laatst bijgewerkt:** 26 november 2025
**Auteur:** Henk - Havun Web Services
**Tech Stack:** Laravel 11 + Filament 3 + Tailwind CSS

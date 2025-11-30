# Technische Keuze - Bert van der Heide Site

> **Besluit: We bouwen de site zelf met Laravel + Filament**
>
> **Datum besluit:** 26 november 2025

---

## Waarom NIET WordPress?

| Probleem | Impact |
|----------|--------|
| Commercieel thema van huidige site | Licentie issues bij kopiëren |
| Veel onnodige knoppen voor Bert | Verwarrend |
| Plugin updates constant nodig | Onderhoudslast |
| Minder controle voor ons | Beperkt door thema |
| Tragere sites | WordPress overhead |

---

## Waarom WEL Laravel + Filament?

| Voordeel | Impact |
|----------|--------|
| 100% controle | Wij + Claude Code bouwen alles zelf |
| Supersimpel admin voor Bert | Alleen wat hij nodig heeft |
| Snelle site | Geen bloat |
| Minimaal onderhoud | Geen plugins, geen thema updates |
| Veilig | Minder aanvalsvectoren dan WordPress |

---

## Wat krijgt Bert?

### Simpel Admin Panel (Filament)

```
┌─────────────────────────────────────────────────────┐
│  🏠 Dashboard                                        │
├─────────────────────────────────────────────────────┤
│                                                     │
│  📄 Pagina's                                        │
│     • Home                    [Bewerken]            │
│     • Over ons                [Bewerken]            │
│     • Diensten                [Bewerken]            │
│     • Contact                 [Bewerken]            │
│                                                     │
│  📝 Blog                                            │
│     • Wat kost een uitvaart   [Bewerken]            │
│     • Crematie vs begrafenis  [Bewerken]            │
│     [+ Nieuwe blog]                                 │
│                                                     │
└─────────────────────────────────────────────────────┘
```

### Bert kan:
- ✅ Teksten aanpassen (klik → type → opslaan)
- ✅ Nieuwe blogs toevoegen
- ✅ Afbeeldingen uploaden
- ✅ Preview bekijken voor publicatie
- ✅ Concept opslaan (nog niet live)
- ✅ Publiceren wanneer klaar

### Bert hoeft NIET:
- ❌ Plugins updaten
- ❌ Thema instellingen begrijpen
- ❌ Technische dingen doen
- ❌ Bang zijn iets stuk te maken

---

## Staging + Preview Strategie

| Wie | Waar | Wat |
|-----|------|-----|
| Henk | staging.bertvanderheide.nl | Technisch werk, nieuwe features |
| Bert | bertvanderheide.nl/admin | Content bewerken via Filament |
| Bert | Production + Preview knop | Concept bekijken voor publicatie |

---

## Content Aanpak

### Wat we overnemen van huidige site:
- ✅ **Teksten** - zijn van Bert
- ⚠️ **Foto's** - alleen eigen foto's (vraag aan Bert!)
- ❌ **Design/thema** - bouwen we opnieuw (vergelijkbaar maar eigen)
- ❌ **Code** - volledig nieuw

### Vragen aan Bert:
```
□ Zijn alle foto's op de site van jou/je fotograaf?
□ Heb je de originele bestanden (hoge resolutie)?
□ Heb je een logo in hoge resolutie (vector/PNG)?
```

---

## Tijdsinschatting

```
Bouwen met Claude Code:
├── Basis site + Filament admin:    8-12 uur
├── Styling + content:              4-6 uur
├── SEO implementatie:              2-4 uur
└── Testen + finetunen:             2-4 uur

Totaal: ~15-25 uur
```

---

## Tech Stack

```
Backend:        Laravel 11
Admin Panel:    Filament 3
Database:       MySQL 8.x
Server:         Nginx op Hetzner VPS
PHP:            8.2
CSS:            Tailwind CSS
```

---

## Site Structuur (Pagina's)

```
Publieke pagina's:
├── Home
├── Over ons / Team
├── Diensten
│   ├── Begrafenis
│   ├── Crematie
│   └── Persoonlijke uitvaart
├── Kosten / Tarieven
├── Veelgestelde vragen (FAQ)
├── Blog (overzicht)
├── Blog artikel (detail)
├── Contact
└── Privacy / Cookies

Admin panel (/admin):
├── Dashboard
├── Pagina's beheren
├── Blog beheren
├── FAQ beheren
├── Instellingen
└── Media bibliotheek
```

---

## Volgende Stappen

1. ☐ Henk bekijkt Filament op YouTube
2. ☐ Contact met Bert (toegang foto's, logo, teksten)
3. ☐ Laravel project opzetten
4. ☐ Filament installeren
5. ☐ Database structuur maken
6. ☐ Admin panel bouwen
7. ☐ Frontend bouwen
8. ☐ Content invoeren
9. ☐ SEO implementeren
10. ☐ Testen op staging
11. ☐ Go-live!

---

**Besluit genomen door:** Henk
**Datum:** 26 november 2025
**Status:** ✅ Definitief - We gaan zelf bouwen!

# CLAUDE.md

This is the central reference for everything related to **Fars Brød**. It covers the business as a whole — brand, voice, operations, content, and digital presence. The website is one part of that picture.

## Business overview

**Fars Brød** is a home bakery in Middelfart, Denmark, run by a single baker. It sells handmade sourdough rolls baked in small batches with real sourdough, long fermentation times, and no additives. Orders are placed online via a HubSpot form and picked up at the baker's home address on Tyttebærkvisten 6, 5500 Middelfart.

The brand voice is warm, personal, and craft-focused — written from the perspective of a father and craftsman, not a company. "Du/dig" throughout. No marketing superlatives.

## Website

Static single-page site in Danish targeting `https://www.farsbrod.dk/`. No build step, no package manager, no framework. Three files:

- `index.html` — all content, structured data (JSON-LD), and inline JS
- `style.css` — all styles, including responsive breakpoints
- `sitemap.xml` / `robots.txt` — SEO support files

### Development

Open `index.html` directly in a browser — no server needed. For a quick local server:

```bash
python3 -m http.server 8080
```

### Architecture

**Single-page layout with anchor navigation.** Sections in order: Hero → Produkter → Om mig → Order CTA → Priser → Find os (address) → FAQ → Footer.

**CSS design tokens** are defined as custom properties on `:root` in `style.css`. The primary palette:
- `--cream` / `--cream-deep` — page backgrounds
- `--dark` / `--dark-mid` — dark sections (about, footer)
- `--brown` / `--gold` — brand accent colors
- `--pad` — section vertical padding (responsive: 6.5rem → 4.5rem → 3.5rem)

**Responsive breakpoints:** 860px (switches two-column grids to single-column, hides photo placeholders) and 600px (mobile nav drawer, tighter spacing).

**Inline JavaScript** (bottom of `index.html`) handles: dynamic copyright year, mobile nav toggle with `aria-expanded`, FAQ accordion via `open` class toggling.

**Order flow** links externally to a HubSpot form. All CTA buttons and nav use the same HubSpot URL — update it in one place if it changes.

**SEO:** Two JSON-LD blocks in `<head>` — `Bakery` schema and `FAQPage` schema. Keep these in sync with visible content when text changes.

**Placeholder content:** The logo box (`<span class="logo-box">`), product image box (`.product-img-box`), and about photo (`.photo-box`) are placeholders awaiting real images. Replace with `<img>` tags when assets are ready.

# INSTRUCTIONS
## Who You Are
You are my content creator, business partner and all round worker for Fars Brød.
## What You Do
- Create content ideas for social media, newsletters and real world activities
- Develop the business, by coming with ideas to optimize the different aspects of Fars Brød, both online and physical
- Analyse the sales and efforts made
## Rules
- Match my tone: Professional, warm, down to earth, sincere
- Never invent stats - flag anything needing a source
- If unclear, ask ONE question before starting
- When you learn something new, add it to claude.md
## What Good Output Looks Like
- Dansk copy er klar til brug — ikke en retningslinje, men færdig tekst med `[X]`-placeholders for data der mangler
- Ingen lange introduktioner eller forklaringer — gå direkte til indholdet
- Brug korte sætninger. To korte frem for én lang med kommaer
- Strukturér med overskrifter når output er langt (f.eks. IDEAS.md)
- Kildehenvisninger med links når der bruges data eller statistikker
- Må gerne gå i tekniske detaljer om bagværk — glutenstruktur, fermentering, enzymaktivitet og lign. — når det er relevant. Tone of voice kan til tider være nørdet, men altid i letforståeligt sprog uden fagtermer der ikke forklares
## Memory
Start of every session: read claude.md
End of every session: update claude.md with new learnings

# MEMORY
## Preferences
- Dansk copy skrives klar til brug — ikke som udkast eller retningslinjer
- Emojis bruges sparsomt og kun hvor de allerede findes i designet
- Tankestreger (—) bruges sparsomt — maks. én per afsnit, og kun når det er den bedste løsning
- Citationstegn i dansk body copy: „..."
- Punktlister afsluttes uden punktum medmindre det er en hel sætning
- Output på dansk medmindre andet er aftalt

## Corrections
- CLAUDE.md dækkede oprindeligt kun hjemmesiden — rettet til at dække Fars Brød som helhed, hjemmesiden er én del af det

## Patterns
- Indholdsidéer gemmes i `IDEAS.md` med statusfelter (`Kvalitet`, `Prioritet`, `Brugt`, `Dato`)
- Ny viden fra sessioner tilføjes til MEMORY-sektionen i CLAUDE.md ved sessionens afslutning
- Dansk copy følger reglerne nedenfor (se Dansk copy-regler)

## Decisions
- Fars Brød kommunikerer på dansk med "du/dig" — aldrig "De/Dem"
- Ingen marketing-superlativer ("Danmarks bedste", "fantastisk", "utrolig")
- Brandet er en person og et håndværk — ikke et firma
- HubSpot (gratis) bruges til bestillingsformular og nyhedsbrev — maks. 1.000 kontakter, 2.000 e-mails/måned, ingen automatiserede workflows
- IDEAS.md er det centrale arbejdsdokument for indhold og forretningsudvikling
- Nyt produkt under overvejelse: frosne Biga-pizzadejskugler til salg om sommeren (se BD12 i IDEAS.md)
- Anbefalet salgspris pizzadej: 20 kr/stk (DG 79% baseret på Dagrofa-priser inkl. moms — se BD12 i IDEAS.md)
- Spiralmikser under overvejelse: EN KYS Pro Baker Easy 5, 6.500 kr — break-even ca. 41 uger ved 10 stk/uge og 20 kr/stk (pizzadej alene), hurtigere inkl. tidsbesparelse på surdejsboller

## Indkøbspriser (verificerede, maj 2026)
- **Caputo Cuoco mel:** 5 kg = 95 kr ekskl. fragt (19 kr/kg) · 25 kg = 449 kr ekskl. fragt fra Pizzafredag (17,96 kr/kg)
- **Caputo Cuoco mel (Dagrofa):** 30 kg = 330 kr ekskl. moms (11 kr/kg ekskl. moms / 13,75 kr/kg inkl. moms) — afhentes selv, ingen fragt
- **Emballage pizzadej (Dagrofa):** Salatbæger 750ml: 50 stk = 43,95 kr ekskl. moms (0,88 kr/stk). Låg: 50 stk = 35,95 kr ekskl. moms (0,72 kr/stk). Samlet VK: 3,35 kr/stk ekskl. moms / 4,19 kr/stk inkl. moms
- **Emballage pizzadej (Lomax.dk):** Delibægre 500ml rPET + låg — 50 bægre (95 kr) + 50 låg (41 kr) + forsendelse = 300,10 kr samlet for 50 sæt = 6,02 kr/stk (ældre pris — Dagrofa er billigere)
- **Dejkugle-spec:** 250g rå dej, ~150g mel, 65% hydrering, én kugle = én pizza
- Mel-forsendelse fra Pizzafredag: ikke verificeret endnu

## Dansk copy-regler
- Tone: varm, personlig, håndværksorienteret — skrevet fra en fars og håndværkers perspektiv
- "du/dig" (uformel tiltale) gennem hele teksten
- Ingen marketing-superlativer
- Korte sætninger — to korte frem for én lang
- Korrekt skriftlig dansk — ingen slang, ingen anglicismer medmindre det er det eneste naturlige ord
- Emojis: kun hvor de allerede eksisterer i designet — ingen nye emojis i body copy, overskrifter eller CTA'er
- Tankestreger (—): sparsomt, maks. én per afsnit, foretruk punktum eller komma
- Citationstegn: „..." i dansk body copy
- Punktlister: ingen afsluttende punktum medmindre punktet er en hel sætning
- Teknisk dybde er velkommen: glutenstruktur, fermentering, enzymaktivitet og lign. må bruges når det er relevant — men altid forklaret i letforståeligt sprog

## Session Progress — Ideas Review
**Status (2026-05-20):** Gennemgang af O-idéer (Organisk social) — nåede til O10.
- O1–O6: Allerede reviewet/markeret i tidligere session
- O7: Dårlig ✓, Ikke nu ✓ (kundereaktioner er upraktisk)
- O8: Dårlig ✓, Ikke nu ✓ (som den er — fin nørdet, men skubbede videre)
- O9: Dårlig ✓, Klar til brug ✓ (udsigt-afhængig, men producerbar)
- O10: Blev ikke markeret — næste session starter her

**Næste:** Fortsæt O10–O14, så Meta Ads (A1–A6), Newsletter (NL1–NL6), Business Dev (BD1–BD11).

## Automatisk månedlig opdatering — 2026-07-01
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (surdejstrends, Hindsgavl Festival, sommerhusmarked):
  - **A17** — Convenience-annonce: "Det eneste du gør er at hente dem"
  - **NL21** — Hindsgavl Festival-uge nyhedsbrev (1.–8. juli 2026)
  - **O42** — Surdej og blodsukker (karrusel, kilde: PMC 2024 meta-analyse)
  - **O43** — Surdejsstarter på ferie (praktisk sommerspørgsmål)
  - **BD23** — Sommerhusmarkedet: radius-targeting 25 km i juli–august
- IDEAS.md pushet til GitHub via lokal git proxy (`git push -u origin main`)
- Git push via personlig PAT i URL-format fejler — brug altid `git push -u origin main` i dette miljø

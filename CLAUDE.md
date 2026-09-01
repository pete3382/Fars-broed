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
- Detached HEAD: brug `git push -u origin HEAD:main` (ikke `git push -u origin main`) når HEAD er detached

## Automatisk månedlig opdatering — 2026-07-05
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 4 nye idéer tilføjet baseret på research (nordisk fermenteringstradition, frysertip, gennemsigtighed som salgsargument, europæisk surdejsforskning):
  - **O49** — Fermentering er nordisk, ikke trendy (karrusel, kilde: Falstaff Fermentation Nation)
  - **O50** — Surdejsboller i fryseren (praktisk fryse/optø-tip til sommerkunder)
  - **A20** — Fire ingredienser. Ingen hemmeligheder. (Meta ad, gennemsigtighed som salgsargument)
  - **NL25** — 1.000 hjemmebagere kortlægges i Europa (newsletter, HealthFerm/Nature 2026)

## Automatisk månedlig opdatering — 2026-07-06
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på juli-sæson, bageteknisk indhold og forretningsudvikling:
  - **A21** — Meta ad: „Du holder ferie. Bollerne gør ikke." (ferievinkel, juli–august radius 25 km)
  - **NL26** — Bollerne i tal (nyt email-format: tal og fakta fra køkkenet)
  - **O51** — Autolyse: Glutennetværket starter af sig selv (bageteknisk nørdet, ny vinkel)
  - **O52** — Fem uger til skolestart (juli-urgency + frysertip til august)
  - **BD27** — Forhåndsbestilling til august: Sikr dine slots nu (forretningsudvikling)
- WebSearch utilgængeligt under denne kørsel — idéer baseret på dokumenteret bageteknisk viden og sæsonlogik

## Automatisk månedlig opdatering — 2026-07-07
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (UPF-trend, surdejsvækst 45% YoY, LIVE Hindsgavl bekræftet 15. aug):
  - **O53** — Hvad er der egentlig i dit brød? (UPF-kontrast, ultraforarbejdede fødevarer 2026)
  - **O54** — Interessen for surdej er vokset 45% på ét år (kilde: Accio/Tribeca Oven 2026)
  - **A22** — Meta ad: LIVE Hindsgavl Slot 15. august (timing: kør 10.–14. august)
  - **NL27** — Hvad ingredienslisten fortæller dig (UPF-vinkel, send primo august)
  - **BD28** — Efterårsklargøring: Kommunikationsplan for september (forretningsudvikling)
- LIVE Hindsgavl Slot bekræftet: 15. august 2026 (kilde: hindsgavl.dk via visitmiddelfart-søgning)

## Automatisk månedlig opdatering — 2026-07-13
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (mæthed/resistent stivelse, GLP-1-madtrend, dansk madkultur 2026, gavekultur, praktisk opbevaring):
  - **O55** — Mæthed, der holder (resistent stivelse og glykæmisk indeks — mæthedsvinklen)
  - **O56** — Brød til at tage med (gavekultur uden anledning — friskbagte boller som hverdagsgave)
  - **A23** — Meta ad: Spis færre ting. Men de rigtige. (GLP-1/quality-over-quantity, kilde: FoodNavigator 2026)
  - **NL28** — Det ved jeg om at gemme surdejsboller (praktisk opbevaring, frysning og brug af rester)
  - **BD29** — Fast ugentlig abonnement: Fars Brød på autopilot (subscription-model, løbende reservation)
- Ny indsigt: Fermentering er gået fra hipster-køkken til hverdagspraksis i Danmark (kilde: Madison/madtrends-2026)
- Ny indsigt: GLP-1 (Ozempic-lignende medicin) er en voksende madtrend i Danmark — folk spiser mindre men vil have bedre kvalitet (kilde: FoodNavigator april 2026)

## Automatisk månedlig opdatering — 2026-07-20
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (augustsæson, surdejsteknik/hydrering, lokal Middelfart-event, dansk bevidst forbrug):
  - **O57** — Augustlyset over bollerne (sæsonbillede, sensommer-stemning, statisk billede)
  - **O58** — Hydrering: Hvad vand gør ved dejen (nørdet karrusel om hydreringsprocent og dejstruktur)
  - **A24** — D-A-D på Tråden 22. august (lokal koncert som bestillingsanledning — kør 17.–21. aug)
  - **NL29** — Surdej og sommervejret (teknisk vidensmail om fermentering i varmen, til primo august)
  - **BD30** — Evaluer sommeren: Hvad virkede, og hvad bør gentages (intern performancereview primo august)
- Ny indsigt: D-A-D spiller på Tråden i Middelfart lørdag 22. august 2026 (kilde: WebSearch)
- Ny indsigt: Dansk madkultur 2026 — reduceret sukker og lokale råvarer som hverdagspraksis er dominerende tendenser (kilde: Madison/madtrends-2026)

## Automatisk månedlig opdatering — 2026-07-27
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (surdejsteknik/teksturtrend, discard/nul-spild, skolestart-transition, august-overblik, madpakke-vinkel):
  - **A25** — Rutinen starter igen (Meta ad til skolestart-transition, kør ultimo juli – primo august)
  - **NL30** — August er her — her er hvad der sker (overbliksbrev med augustkalender: Hindsgavl, D-A-D, Klimafolkemødet)
  - **O59** — Knaset: Hvad der sker i skorpen (teknisk nørdet om maillard/damp/tekstur — teksturtrend 19% vækst i 2026)
  - **O60** — Discarden: Hvad sker der med det der tages ud? (zero-waste/discard-trend — pandekager, knækbrød, vafler)
  - **BD31** — Madpakke-vinklen: Surdejsboller til hverdag og skoletaske (ny brugsvinkel til skolestart)
- Ny indsigt: Consumer interest in crunchy textures up 19% in 2026 (kilde: Accio/Bread Trends 2026)
- Ny indsigt: Sourdough discard/zero-waste baking er en voksende trend i 2026 — nul-spild som indholdsvinkel (kilde: deliveryrank.com/bakingstarter.com)
- Ny indsigt: Copenhagen Cooking 2026 afholdes 21.–30. august i København med æblet som tema

## Automatisk månedlig opdatering — 2026-08-01
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (surdejsteknik/teksturkontrast, NiMe-mikrobiomforskning, Gelsted Marked, dansk lokalheds-trend):
  - **A26** — Gelsted Marked 2026 (Meta ad 9.–12. august, Fyns største marked 13.–16. august)
  - **NL31** — Fermentering som det nye grundkøkken (NiMe-diet, Probiota 2026, send primo august)
  - **O61** — Det første bid (teksturkontrast: sprød skorpe + sej krumme, surdej som supertrend)
  - **O62** — Lavet i Danmark. Bagt i Middelfart. (dansk lokalheds-signal som kvalitetsstempel)
  - **BD32** — Gelsted Marked: Undersøg mulighed for stand eller salgspunkt (fysisk tilstedeværelse)
- Ny indsigt: Gelsted Marked afholdes 13.–16. august 2026 — et af Fyns største markeder med 350+ handlende (kilde: VisitMiddelfart.com)
- Ny indsigt: NiMe-diet (Non-industrialized Microbiome Restore) fra Probiota 2026 — fermenterede fødevarer positioneres som klinisk relevant for tarmflora-diversitet (kilde: NutraIngredients/Probiota 2026)
- Ny indsigt: Surdej bekræftet som global supertrend i 2026 — markedet vurderet til USD 4,9 mia, vækst mod USD 7,35 mia i 2034 (kilde: Fortune Business Insights / Puratos Taste Tomorrow)
- Ny indsigt: "Danskhed" som kvalitetssignal — dansk forbrugerforskning 2026 viser at lokal oprindelse er en stærk tillids- og kvalitetsdriver (kilde: Innova Market Insights)

## Automatisk månedlig opdatering — 2026-08-02
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (high-protein trend, solformørkelse 12. aug, efterårsskifte, sensommerbrev, rugmel-variant):
  - **O63** — Frøene giver dig mere end knas (karrusel, high-protein trend 2026 +17%)
  - **O64** — Solformørkelsen 12. august (Story/statisk, lokal anledning, post 10.–11. aug)
  - **A27** — September nærmer sig — start den godt (Meta ad, overgang sommer→hverdag)
  - **NL32** — Sommer er ved at ebbe ud (personligt augustbrev, send 9.–13. august)
  - **BD33** — Rugmel-variant til efteråret: Test en ny produktidé (sæsonvariant, fiber-trend 2026)
- Ny indsigt: Solformørkelse delvist synlig over Danmark 12. august 2026 (kilde: lex.dk)
- Ny indsigt: High-protein bagværk er den hurtigst voksende trend i 2026 — samtaler om proteinrigt bagværk vokser 17% YoY (kilde: Chewco / Accio Bread Trends 2026)
- Ny indsigt: Fiber er den største maddagsorden i Danmark 2026 — "Fiber, kål og kødet er tilbage" (kilde: Mandekogebogen.dk)

## Automatisk månedlig opdatering — 2026-08-03
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (efterårsskifte/surdejstemperatur, Fredericia Streetfood Festival, september-sæson):
  - **A28** — Fredericia Streetfood Festival (Meta ad, radius 40 km, kør 1.–4. september)
  - **NL33** — Det køle i luften (september-sæsonbrev, send 1.–3. september)
  - **O65** — Hvad kulden gør ved surdejen (teknisk nørdet, sommer→efterår-overgang)
  - **O66** — September: Frisk start, langsom morgen (sæsonstatisk, efterårsmorgen)
  - **BD34** — Fredericia Streetfood Festival: Nå ud til en ny målgruppe (koordineret sept-indsats)
- Ny indsigt: Fredericia Streetfood Festival afholdes ca. 5.–8. september 2026 (~30 km fra Middelfart, Trekantområdet) — kilde: fredericiashopping.dk
- Ny indsigt: Food Festival Aarhus 2026 (4.–6. sept) har æblet som årets råvare — første gang det er en frugt (kilde: Things to Do in Denmark)
- Ny indsigt: Koldere vejr favoriserer mælkesyre frem for eddikesyre i surdejsfermentering — efterårsbollerne smagsmæssigt rundere og mildere end sommerboller

## Automatisk månedlig opdatering — 2026-08-06
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (heritage korn-renæssance, surdejskemi mælkesyre/eddikesyre, mandagsmorgen-overgang, august personligt brev, ølandshvede produkttest):
  - **A29** — Mandagsmorgenerne er på vej igen (Meta ad, overgang sommerferie→hverdagsrytme, primo aug–primo sept)
  - **NL34** — August i køkkenet (personlig augusthilsen fra bagerperspektiv, send 4.–7. august)
  - **O67** — De gamle korn vender tilbage (karrusel, ølandshvede/spelt/emmer, heritage grain-renæssance)
  - **O68** — To syrer. Et bid. (teknisk nørdet, mælkesyre vs eddikesyre, sæsonvariation i surdej)
  - **BD35** — Ølandshvede-variant: Test en premium efterårsbolle (ny produkttest, 20–30% ølandshvede)
- Ny indsigt: Heritage korn (ølandshvede, spelt, emmer) oplever renæssance i 2026 — forbrugere forbinder dem med autenticitet og lokale råvarer (kilde: BKD madtendenser-2025)
- Ny indsigt: Ølandshvede absorberer anderledes end standardhvede — hydreringsjustering nødvendig ved test
- Ny indsigt: Fytinsyreindhold i ølandshvede reduceres effektivt af surdejsfermentering — mineraloptagelse forbedres (faglig vinkel til indhold)
- Ny indsigt: Arabinoxylaner i kerner er et kommende funktionelt ingrediens-fokusområde i 2026 — relevant for teknisk indhold om fuldkorn

## Automatisk månedlig opdatering — 2026-08-06 (kørsel 2)
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (surdejscroissant-trend, Food Festival Aarhus september, 217%-søgestigning, batch-identitet):
  - **A31** — 217% flere søger hjemmebagt surdej — vi bager det for dig (Meta ad, data-drevet)
  - **NL36** — Food Festival Aarhus 4.–6. september (nyhedsbrev, send 1.–3. sept)
  - **O71** — Surdejscroissanten og hvad den siger om surdej (karrusel, kulturkommentar, trend 2026)
  - **O72** — Et hold ad gangen (statisk billede, brand-identitetspost)
  - **BD37** — Food Festival Aarhus 4.–6. september: Besøg som producent (forretningsudvikling, research-trip)
- Ny indsigt: Søgninger efter hjemmebagt surdej steg 217% det seneste år (kilde: Food Drink Life, 2026)
- Ny indsigt: Surdejscroissanter er 2026's hurtigst voksende bagværkssøgning (kilde: Atome Bakery, 2026)
- Ny indsigt: Food Festival Aarhus afholdes 4.–6. september 2026 på Tangkrogen — 30.000 gæster, 250 producenter (kilde: gogoevents.dk)

## Automatisk månedlig opdatering — 2026-08-07
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (sundere brød-trend, surdejsfermentering sommer→efterår, dampens rolle i skorpedannelse, kold hævning, Google-anmeldelser):
  - **A32** — Det sunde brød er ikke altid det, du tror (Meta ad, sundere-alternativ-vinkel, kilde: State of the Industry 2026)
  - **NL37** — Hvad der sker med surdejen de næste fire uger (teknisk/personlig overgangsmail, mælkesyre vs eddikesyre i augusttemperaturen)
  - **O73** — De ti minutter der bestemmer skorpen (karrusel, bageteknisk nørdet, dampens rolle og skorspedannelse)
  - **O74** — Bagt mens du sov (statisk, natten og kold hævning, fermentering som stille arbejde)
  - **BD38** — Google-anmeldelser: September-push for lokal synlighed (struktureret kampagne til lokal Google Maps-tilstedeværelse)
- Ny indsigt: Brødbranchen 2026 viser klart skifte mod sundere alternativer — surdej positioneres som klinisk relevant valg (kilde: State of the Industry 2026, Snack Food & Wholesale Bakery)
- Ny indsigt: Damp i ovnen i de første 10 minutter er afgørende for sprød skorpe — fordi overfladen holdes fugtig og dejen kan ekspandere frit før skorpen sætter sig
- Ny indsigt: Google Business-profil og anmeldelsesantal er stærke faktorer for lokal søgeranglering i Middelfart-radius

## Automatisk månedlig opdatering — 2026-08-10
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (surdej og tarmflora/laktobacillus, skolestart august, fermentering og ernæring/fytinsyre, fysisk/håndgjort som 2026-tendens, julegavepakke):
  - **A33** — Bollerne sidder klar. Skolen starter igen. (Meta ad, skolestart-uge 10.–16. august, familiemålgruppe)
  - **NL38** — Fermenteringen gør noget ved melet (vidensmail, fytinsyre-nedbrydning, mineraloptagelse, lavere GI, send 1.–5. september)
  - **O75** — Laktobacillus: Surdej og tarmfloraen (karrusel, laktobacillus-familien, fytinsyre, mineraloptagelse — kilde: NCBI/PMC 2024)
  - **O76** — Det konkrete vinder (statisk, 2026-tendens om det fysiske og håndgjorte — kilde: DR trendspot 2026)
  - **BD39** — Julegave-pakke: Planlæg nu til november (fire boller i papirkasse med hilsen, begrænset antal, nyhedsbrevsmodtagere)
- Ny indsigt: Laktobacillus-bakterierne i surdej nedbryder fytinsyre — frigiver jern, zink og magnesium som kroppen ellers ikke optager fra melet (kilde: NCBI/PMC 2024)
- Ny indsigt: Dansk trendforskning 2026 peger på „behov for det fysiske og håndgribelige" som en af de store tendenser — modreaktion mod digitalisering (kilde: DR/TV2 januar 2026)
- Ny indsigt: 188 danske skoler deltager i nationalt pilotprogram for gratis skolemåltider (2025–2028) — men størstedelen af børn tager stadig madpakke (kilde: fao.org / feast2030.eu)

## Automatisk månedlig opdatering — 2026-08-17
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (Klimafolkemødet Middelfart, surdej som præbiotikum, clean label-trend, lokal event-synlighed):
  - **A34** — Klimafolkemødet 27.–29. august i Middelfart (Meta ad, radius 25 km, kør 24.–28. august)
  - **NL39** — Klimafolkemødet og det, vi bager (personligt nyhedsbrev, send 25. august)
  - **O77** — Tre bakterier. Ét brød. (karrusel, surdej som præbiotikum — Akkermansia, Bifidobacterium, Lactobacillus)
  - **O78** — Du ved, hvad der er i det. (statisk, clean label / "Return to Real"-trend)
  - **BD40** — Klimafolkemødet: Mød lokale og bliv set (forretningsudvikling, netværk og fremtidig salgskanal)
- Ny indsigt: Klimafolkemødet afholdes 27.–29. august 2026 på KulturØpladsen i Middelfart — gratis og åbent for alle (kilde: klimafolkemoedet.dk)
- Ny indsigt: Surdej øger mængden af Akkermansia, Bifidobacterium og Lactobacillus i tarmen — via exopolysaccharider produceret under fermentering (kilde: Frontiers in Microbiology, 2022)
- Ny indsigt: "Return to Real" er en stærk global forbrugertrend i 2026 — clean labels og at vide hvad der er i maden driver surdejsvækst (kilde: Atome Bakery / Snack Food & Wholesale Bakery 2026)
- Ny indsigt: Middelfart Sejlklub afholder stævne 28. august – 6. september 2026 (potentiel lokal event-vinkel til fremtidige kørselER)

## Automatisk månedlig opdatering — 2026-08-24
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (fibermaxxing 2026, rugbrødstradition, dansk surdejsscene, sensommer-overgang):
  - **A35** — Første kølige morgen — bollerne er varme (Meta ad, sensommer→efterårsovergang, kør 25. august – 7. september)
  - **NL40** — Sensommerens sidste weekender (personligt nyhedsbrev, send 26.–28. august)
  - **O79** — Fibermaxxing: Bollen som naturlig fiberkilde (karrusel, 2026-fibertrend + frø + resistent stivelse)
  - **O80** — Rugbrød og bollen: To sider af samme håndværk (kulturhistorisk vinkel, dansk surdejstradition)
  - **BD41** — Positioner Fars Brød i den danske surdejsscene (forretningsudvikling, samhørighed med små danske mikrobagerier)
- Ny indsigt: „Fibermaxxing" er en af de største danske madtrends i 2026 — 2025 handlede om protein, 2026 handler om fiber (kilde: Mandekogebogen.dk / Madison)
- Ny indsigt: Sourdough-samtaler er vokset 17,98% på et år — trenden er fortsat med at vokse fem år efter pandemistart (kilde: Food Drink Life 2026)
- Ny indsigt: Simpel Surdej i Viborg er blevet en af de mest anerkendte europæiske surdejsbrands — dansk mikrobageri-scene har international synlighed (kilde: All Things Nordic)
- Ny indsigt: Koldere fermentering (efterårstemperaturer) favoriserer mælkesyre frem for eddikesyre — det er en solid teknisk vinkel til september-kommunikation

## Automatisk månedlig opdatering — 2026-09-01
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (Sourdough September, oktober-overgang, sæsonfermentering, lokal event-strategi):
  - **A37** — Oktober: Start måneden rigtigt (Meta ad, kør hele oktober)
  - **NL42** — Hvad september lærte mig (personligt måneds-opsummering, send 28.–30. september)
  - **O83** — #SourdoughSeptember: Del dit morgenøjeblik (engagement Story/opslag, brug i uge 2–3 september)
  - **O84** — Efterårsbollen er en anelse mildere (statisk, sensorisk beskrivelse af efterårsboldens smagsændring)
  - **BD43** — Oktober-events på Hindsgavl Slot: Lokale bestillingsanledninger (forretningsudvikling, events 4./10./24. okt — verificér på hindsgavl.dk)
- Ny indsigt: Crunchy textures +19% i 2026 — sprød skorpe er et stærkt salgsargument i september-oktober (kilde: Accio/Bread Trends 2026)
- Ny indsigt: Sourdough September 2026 er i fuld gang — #SourdoughSeptember som globalt hashtag bekræftet (kilde: Real Bread Campaign / sustainweb.org)
- Ny indsigt: Hindsgavl Slot har events i oktober 2026 (4., 10. og 24. oktober nævnt) — specificér eventtyper ved at verificere på hindsgavl.dk inden publicering

## Automatisk månedlig opdatering — 2026-08-31
- Bot-kørslen arkiverede 0 idéer (ingen opfyldte arkiveringskriterierne)
- 5 nye idéer tilføjet baseret på research (Sourdough September international kampagne, sæsonbetonet indhold primo september, danske rodfrugter i sæson):
  - **A36** — September er surdejens måned (Meta ad, kør hele september, Sourdough September-platformen)
  - **NL41** — September er surdejens måned (nyhedsbrev, send 1.–2. september)
  - **O81** — September er surdejens måned (karrusel, Sourdough September international kampagne, #SourdoughSeptember)
  - **O82** — Rodfrugterne er tilbage (statisk billede, dansk sæsonindhold september, rodfrugtssuppe + bolle)
  - **BD42** — Sourdough September: Planlæg månedskampagnen (koordineret kommunikationsplan for hele september)
- Ny indsigt: Sourdough September er en international kampagne (Real Bread Campaign, UK) der løber hele september — #SourdoughSeptember er et globalt hashtag med bred organisk rækkevidde (kilde: sustainweb.org/realbread)
- Ny indsigt: Sourdough-produktlanceringer steg 31% i 2026 — "Return to Real" driver væksten globalt (kilde: Puratos / Atome Bakery 2026)
- Ny indsigt: September er sæson for rodfrugter i Danmark — pastinak, jordskokke, persillerod og knoldselleri er alle i sæson primo september (kilde: iform.dk)

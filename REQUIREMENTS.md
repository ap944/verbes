# Requirements — Verbes
_Laatst bijgewerkt: 2026-05-17_

## Doel
Een mobiel-vriendelijke flashcard-app voor het leren van Franse werkwoordsvervoegingen, gebaseerd op het boek "Even spieken? Werkwoorden Frans" (Intertaal, 2021). De app volgt een strikte blokvolgorde van 8 hoofdblokken met sub-blokken, gebruikt multiple choice als interactievorm, en past SM-2 spaced repetition toe. Doelgebruiker: Auke. Platform: browser (single HTML file, offline via localStorage).

---

## Eisenboom

### Stakeholdereisen (SR)

| ID | Eis | Status |
|----|-----|--------|
| SR-1 | De gebruiker moet alle Franse werkwoordsvervoegingen uit het boek "Even spieken?" kunnen leren via flashcards | |
| SR-2 | De gebruiker moet zijn voortgang visueel kunnen volgen op een startscherm met concentrische ringen | |
| SR-3 | De gebruiker moet in een vaste blokvolgorde door de stof werken zonder blokken te kunnen overslaan | |
| SR-4 | De gebruiker moet vrij kunnen oefenen (geen verplicht dagritme) | |
| SR-5 | De gebruiker moet voortgang kunnen exporteren en importeren als backup | |
| SR-6 | De app moet er visueel hetzelfde uitzien als de Flash cards woordenschat-app (donker thema, zelfde structuur) | |
| SR-7 | De gebruiker moet bij elk nieuw blok een korte grammatica-uitleg kunnen lezen en later terughalen | |

### Systeemeisen (SyR)

| ID | Eis | Afgeleid van | Test/check | Status |
|----|-----|-------------|------------|--------|
| **Kaartinteractie** | | | | |
| SyR-1.1 | Het systeem moet multiple choice met 4 antwoordknoppen tonen per vraag | SR-1 | Inspectie: 4 knoppen zichtbaar per kaart | |
| SyR-1.2 | Afleiders moeten andere vervoegingsvormen van hetzelfde werkwoord zijn | SR-1 | Inspectie: afleiders komen uit dezelfde vervoegingstabel | |
| SyR-1.3 | FR→NL fase: de gebruiker ziet een Franse vervoeging en kiest de juiste persoon+tijd (grammaticale analyse) | SR-1 | Test: FR→NL kaart toont vervoeging, opties zijn persoon/tijd-combinaties | |
| SyR-1.4 | NL→FR fase: de gebruiker ziet een Nederlandse beschrijving (werkwoord+persoon+tijd) en kiest de juiste Franse vervoeging | SR-1 | Test: NL→FR kaart toont prompt, opties zijn vervoegingsvormen | |
| SyR-1.5 | Mix-fase: willekeurige combinatie van FR→NL, NL→FR en infinitief+persoon→vorm door elkaar | SR-1 | Test: mix-kaarten wisselen random tussen de drie typen | |
| SyR-1.6 | Na elk antwoord moet directe feedback verschijnen (goed/fout + juiste antwoord) | SR-1 | Inspectie: feedback zichtbaar na keuze | |
| SyR-1.7 | De voorbeeldzin moet altijd zichtbaar zijn onder de vraag in kleiner, grijs lettertype | SR-1 | Inspectie: voorbeeldzin permanent zichtbaar onder vraag | |
| SyR-1.8 | Bij elk antwoord (goed of fout) moet een mini-uitleg verschijnen met de vormingsregel (bijv. "Présent -er: stam + -e, -es, -e, -ons, -ez, -ent") | SR-1 | Inspectie: vormingsregel zichtbaar na antwoord bij alle werkwoorden | |
| SyR-1.9 | Bij spelling-bijzonderheden moeten de afwijkende letters in oranje/amber (#f0a500) gemarkeerd zijn | SR-1 | Inspectie: oranje markering op afwijkende letters | |
| **Blokstructuur** | | | | |
| SyR-2.1 | Het systeem moet 8 hoofdblokken bevatten in vaste volgorde: (1) Hulpwerkwoorden présent, (2) Regelmatig présent, (3) Spelling-bijzonderheden, (4) Futur proche + impératif, (5) Passé composé, (6) Imparfait + conditionnel, (7) Onregelmatige werkwoorden, (8) Bijzondere vormen + gevorderde tijden | SR-3 | Inspectie: 8 blokken in juiste volgorde | |
| SyR-2.2 | Elk hoofdblok bevat sub-blokken (4-7 per blok) die elk apart beheerst moeten worden | SR-3 | Inspectie: sub-blokken aanwezig per hoofdblok | |
| SyR-2.3 | Een sub-blok gebruikt een 6-fasen beheersingstest per kaart (phaseProgress 0-5): 0-1 FR→NL, 2-3 NL→FR, 4-5 mix. Fasevoortgang is per kaart, niet globaal | SR-3 | Test: faseovergang alleen bij correct voltooien | ✅ Geverifieerd |
| SyR-2.4 | Een hoofdblok-toets van 12 kaarten in mix-modus moet afgelegd worden bij voltooiing van alle sub-blokken. Score ≥80% ontgrendelt het volgende hoofdblok | SR-3 | Test: toets verschijnt, <80% blokkeert volgende blok | |
| SyR-2.5 | Vergrendelde blokken moeten visueel als vergrendeld getoond worden (niet klikbaar) | SR-3 | Inspectie: locked-state zichtbaar | |
| SyR-2.6 | Passé simple (blok 8.7) mag alleen in de FR→NL herkenningsfase aangeboden worden, nooit als productie | SR-1 | Test: passé simple verschijnt nooit in NL→FR of mix | |
| **Werkwoorden & data** | | | | |
| SyR-3.1 | Het systeem moet alle werkwoorden uit het boek "Even spieken? Werkwoorden Frans" bevatten (~60+ werkwoorden) | SR-1 | Tel: alle werkwoorden uit boek aanwezig in data-array | |
| SyR-3.2 | Alle tijden uit het methodedocument moeten ondersteund worden: présent, futur proche, impératif, passé composé, imparfait, conditionnel, futur simple, subjonctif, passé simple (herkenning), gérondif/participe présent | SR-1 | Tel: alle genoemde tijden aanwezig | |
| SyR-3.3 | Per werkwoord per tijd moet een voorbeeldzin (FR + NL) gegenereerd worden | SR-1 | Tel: voorbeeldzin aanwezig per werkwoord per tijd | |
| SyR-3.4 | Bij wederkerende werkwoorden (se laver etc.) moet het wederkerend voornaamwoord onderdeel zijn van de antwoordopties | SR-1 | Test: wederkerend vnw in opties, niet vooraf gegeven | |
| SyR-3.5 | Bij passé composé moet het hulpwerkwoord + deelwoord (incl. akkoord) als één antwoord gepresenteerd worden | SR-1 | Test: être/avoir + deelwoord als geheel in opties | |
| **Voortgangsvisualisatie** | | | | |
| SyR-4.1 | Het startscherm moet twee concentrische SVG-ringen tonen: buitenring = 8 hoofdblokken, binnenring = sub-blokken van het actieve hoofdblok | SR-2 | Inspectie: twee ringen zichtbaar met juiste segmenten | |
| SyR-4.2 | Ringsegmenten moeten kleuren tonen op basis van status: locked (donker), empty (grijs), in-progress (groen varianten), gold (volledig beheerst interval ≥21d) | SR-2 | Inspectie: kleuren kloppen per status | |
| SyR-4.3 | Geen tekstuele voortgangsindicator bovenaan — alleen visuele ringen | SR-2 | Inspectie: geen tekst boven ringen | |
| SyR-4.4 | Een "Start sessie"-knop moet centraal in de binnenring geplaatst zijn | SR-2, SR-4 | Inspectie: knop aanwezig en werkend | |
| **Sessies** | | | | |
| SyR-5.1 | Een sessie bestaat uit 25 kaarten | SR-4 | Tel: sessie bevat 25 kaarten | |
| SyR-5.2 | Vrij oefenen: geen sessielimiet of dagritme-tracking | SR-4 | Inspectie: geen sessie-cap of dagindeling | |
| SyR-5.3 | De sessiesamenstelling moet adaptief zijn (verhouding nieuw/review op basis van recente scores, zoals Flash cards) | SR-1 | Test: meer review bij lage scores | |
| **SRS (Spaced Repetition)** | | | | |
| SyR-6.1 | Het systeem moet SM-2 adaptief spaced repetition gebruiken (ease-factor, interval, streak) identiek aan Flash cards | SR-1 | Inspectie: SM-2 algoritme aanwezig | |
| SyR-6.2 | Bij fout in review-sessie valt de kaart terug naar fase 4 (mix-fase), niet helemaal naar fase 1 | SR-1 | Test: review-fout → fase 4 | |
| SyR-6.3 | Bij fout binnen een sub-blok wordt de kaart pas na 3 andere kaarten opnieuw aangeboden | SR-1 | Test: fout-kaart verschijnt niet direct opnieuw | |
| **Uitlegschermen** | | | | |
| SyR-7.1 | Bij het openen van een nieuw hoofdblok verschijnt een uitlegscherm met: wanneer gebruik je deze tijd (2-3 zinnen), vormingsregel (1 regel), illustratieve voorbeeldzin | SR-7 | Inspectie: uitlegscherm verschijnt bij nieuw blok | ✅ Geverifieerd |
| SyR-7.2 | Het uitlegscherm moet altijd terug te halen zijn via een icoon rechtsboven tijdens het oefenen | SR-7 | Test: icoon opent uitlegscherm | ✅ Geverifieerd |
| SyR-7.3 | Het uitlegscherm (boek-icoon) moet tijdens een sessie de grammatica tonen van het werkwoord op de huidige kaart, met werkwoord-specifieke regel, uitgangen en voorbeelden | SR-7 | Test: bij finir toont -ir regels, bij parler -er regels | |
| SyR-7.4 | Bij onregelmatige werkwoorden (être, avoir, faire, etc.) moet het uitlegscherm de volledige vervoegingstabel tonen i.p.v. een generieke regel | SR-7 | Inspectie: onregelmatig werkwoord toont alle 6 vormen | |
| SyR-7.5 | Bij spelling-bijzonderheden (manger, acheter, appeler) moet het uitlegscherm de bijzonderheid apart benoemen naast de standaard -er regel | SR-7 | Inspectie: bijzonderheid zichtbaar | |
| SyR-7.6 | De mini-uitleg na elk antwoord (vormingsregel in feedback) moet ook werkwoord-specifiek zijn | SR-1 | Test: feedback toont juiste regel per werkwoordtype | |
| SyR-7.7 | Vanuit het homescreen toont het boek-icoon een overzicht van alle werkwoordtypes van het actieve blok | SR-7 | Inspectie: overzicht zichtbaar | |
| **UI & thema** | | | | |
| SyR-8.1 | Donker thema identiek aan Flash cards: achtergrond #0d1117, zelfde kleurenpalet | SR-6 | Inspectie: kleuren kloppen | |
| SyR-8.2 | Het icoon moet hetzelfde ontwerp zijn als Flash cards maar in groene kleur | SR-6 | Inspectie: icoon groen, zelfde vorm | |
| SyR-8.3 | De app heet "Verbes" — dit moet in de titel, header en metadata staan | SR-6 | Inspectie: naam correct overal | |
| SyR-8.4 | Confetti-animatie bij fase-voltooiing, sub-blok klaar, hoofdblok klaar (zelfde systeem als Flash cards) | SR-6 | Test: confetti verschijnt bij mijlpalen | |
| SyR-8.5 | Geen hints op kaarten | SR-1 | Inspectie: geen hint-UI aanwezig | |
| SyR-8.6 | Geen placement test — iedereen begint bij blok 1 | SR-3 | Test: app start altijd bij blok 1.1 | |
| SyR-8.7 | Alle iconen moeten Feather-style stroke SVG zijn (geen emoji) | SR-6 | Inspectie: geen emoji-iconen in UI | |
| **Persistentie & settings** | | | | |
| SyR-9.1 | Voortgang wordt opgeslagen in localStorage | SR-5 | Test: herstart behoudt voortgang | |
| SyR-9.2 | Export-functie: voortgang als JSON downloadbaar | SR-5 | Test: export produceert geldig JSON | |
| SyR-9.3 | Import-functie: JSON-bestand herstelt voortgang | SR-5 | Test: import herstelt state correct | |
| SyR-9.4 | Settings-scherm met: voortgang resetten, backup exporteren, backup importeren | SR-5 | Inspectie: settings bevat alle drie opties | |
| SyR-9.5 | Single HTML file — alle code, CSS en data inline | SR-6 | Inspectie: één .html bestand, geen externe deps | |
| **Duplicaatvormen** | | | | |
| SyR-10.1 | Bij werkwoorden met identieke vervoegingsvormen voor meerdere personen (bijv. je/il parle) moeten alle correcte personen als juist antwoord geaccepteerd worden | SR-1 | Test: beide personen scoren correct | ✅ Geverifieerd |
| SyR-10.2 | Bij een fout antwoord op een duplicaatvorm moet de feedback alle correcte personen tonen (bijv. "je (présent) / il/elle (présent)") | SR-1 | Inspectie: feedback toont alle opties | ✅ Geverifieerd |
| SyR-10.3 | Afleiders mogen geen duplicaten bevatten van het correcte antwoord (personen met dezelfde vorm worden uitgesloten als afleider) | SR-1 | Test: afleiders bevatten geen identieke vormen | ✅ Geverifieerd |
| **Performance** | | | | |
| SyR-11.1 | Werkwoorddata moet via O(1) lookup beschikbaar zijn (VERB_MAP hash) in plaats van lineaire scan | SR-1 | Inspectie: VERB_MAP aanwezig | ✅ Geverifieerd |

---

## Functieboom

### Top-level functies

| ID | Functie | Dekt SyR |
|----|---------|----------|
| F1 | Kaarten presenteren en beoordelen | SyR-1.1 t/m SyR-1.9, SyR-10.1 t/m SyR-10.3 |
| F2 | Blokvoortgang beheren | SyR-2.1 t/m SyR-2.6 |
| F3 | Werkwoorddata leveren | SyR-3.1 t/m SyR-3.5 |
| F4 | Voortgang visualiseren | SyR-4.1 t/m SyR-4.4 |
| F5 | Sessies samenstellen | SyR-5.1 t/m SyR-5.3 |
| F6 | Spaced repetition berekenen | SyR-6.1 t/m SyR-6.3 |
| F7 | Grammatica-uitleg tonen | SyR-7.1, SyR-7.2 |
| F8 | UI renderen (thema, animaties) | SyR-8.1 t/m SyR-8.7 |
| F9 | Data persisteren en herstellen | SyR-9.1 t/m SyR-9.5 |

### Volledige boom

```
F1 Kaarten presenteren en beoordelen
├── F1.1 Multiple choice vraag tonen (4 opties)
│   ├── F1.1.1 FR→NL vraag genereren (vervoeging → persoon+tijd)
│   ├── F1.1.2 NL→FR vraag genereren (beschrijving → vervoeging)
│   └── F1.1.3 Mix vraag genereren (random type)
├── F1.2 Afleiders selecteren (zelfde werkwoord, andere vormen)
├── F1.3 Voorbeeldzin tonen (altijd zichtbaar, onder vraag, klein)
├── F1.4 Feedback tonen (goed/fout + juist antwoord)
├── F1.5 Vormingsregel tonen na antwoord
├── F1.6 Spelling-bijzonderheden markeren (oranje #f0a500)
├── F1.7 Wederkerend voornaamwoord in antwoord opnemen
├── F1.8 Passé composé: hulpww+deelwoord als één optie
└── F1.9 Duplicaatvormen detecteren en alle correcte personen accepteren

F2 Blokvoortgang beheren
├── F2.1 8 hoofdblokken in vaste volgorde beheren
├── F2.2 Sub-blokken per hoofdblok tracken
├── F2.3 6-fasen beheersingstest per sub-blok uitvoeren
│   ├── F2.3.1 Fase 1-2: FR→NL (2 rondes)
│   ├── F2.3.2 Fase 3-4: NL→FR (2 rondes)
│   └── F2.3.3 Fase 5-6: Mix (2 rondes)
├── F2.4 Hoofdblok-toets afnemen (12 kaarten, ≥80%)
├── F2.5 Blokken vergrendelen/ontgrendelen
└── F2.6 Passé simple beperken tot herkenning

F3 Werkwoorddata leveren
├── F3.1 Alle werkwoorden uit boek opslaan (~60+)
├── F3.2 Vervoegingen per werkwoord per tijd per persoon
├── F3.3 Voorbeeldzinnen per werkwoord per tijd (FR+NL)
├── F3.4 Metadata: regelmatig/onregelmatig/spelling-bijzonderheid
└── F3.5 Wederkerende werkwoorden met voornaamwoorden

F4 Voortgang visualiseren
├── F4.1 SVG buitenring tekenen (8 hoofdbloksegmenten)
├── F4.2 SVG binnenring tekenen (sub-blokken actief blok)
├── F4.3 Segmentkleuren bepalen (locked/empty/progress/gold)
└── F4.4 Start-sessie-knop centraal plaatsen

F5 Sessies samenstellen
├── F5.1 25 kaarten selecteren per sessie
├── F5.2 Nieuw/review-verhouding adaptief bepalen
└── F5.3 Foute kaarten uitstellen (3 kaarten wachten)

F6 Spaced repetition berekenen
├── F6.1 SM-2 algoritme toepassen (ease, interval, streak)
├── F6.2 Review-terugval naar fase 4 bij fout
└── F6.3 Due-date berekenen per kaart per richting

F7 Grammatica-uitleg tonen
├── F7.1 Uitlegscherm bij nieuw blok (gebruik, regel, voorbeeld)
├── F7.2 Terug-te-halen via icoon rechtsboven
├── F7.3 Werkwoord-specifieke tense-info tonen (regel, uitgangen, voorbeeld per type)
├── F7.4 Volledige vervoegingstabel bij onregelmatige werkwoorden
├── F7.5 Spelling-bijzonderheden apart benoemen
├── F7.6 Werkwoord-specifieke mini-uitleg in antwoordfeedback
└── F7.7 Blok-overzicht tonen vanuit homescreen

F8 UI renderen
├── F8.1 Donker thema (#0d1117) toepassen
├── F8.2 Groen icoon genereren
├── F8.3 App-naam "Verbes" tonen
├── F8.4 Confetti-animatie bij mijlpalen
└── F8.5 Feather-style SVG iconen gebruiken

F9 Data persisteren
├── F9.1 State opslaan in localStorage
├── F9.2 Voortgang exporteren als JSON
├── F9.3 Voortgang importeren uit JSON
└── F9.4 Settings-scherm renderen (reset/export/import)
```

---

## Objectenboom

| ID | Component | Type | Implementeert functies |
|----|-----------|------|----------------------|
| O1 | `verbes.html` | HTML file | Alle functies (single file) |
| O1.1 | `<style>` blok | CSS | F8.1, F8.5 (thema, iconen) |
| O1.2 | `VERBS` data-array + `VERB_MAP` hash | JS data | F3.1 t/m F3.5 (werkwoorddata, O(1) lookup) |
| O1.3 | `TENSE_INFO` object | JS data | F7.1 (grammatica-uitleg per tijd) |
| O1.4 | `SPELLING_RULES` object | JS data | F1.5, F1.6 (vormingsregels, markering) |
| O1.5 | Scherm: Home | HTML+JS | F4.1 t/m F4.4 (ringen, startknop) |
| O1.6 | Scherm: Session | HTML+JS | F1.1 t/m F1.8, F5.1 t/m F5.3 |
| O1.7 | Scherm: Summary | HTML+JS | F8.4 (sessie-resultaat, confetti) |
| O1.8 | Scherm: Block Test | HTML+JS | F2.4 (hoofdblok-toets) |
| O1.9 | Scherm: Tense Info | HTML+JS | F7.1, F7.2 (uitlegscherm) |
| O1.10 | Scherm: Settings | HTML+JS | F9.4 (reset/export/import) |
| O1.11 | Scherm: Celebration | HTML+JS | F8.4 (blok-voltooiing viering) |
| O1.12 | Module: SRS Engine | JS | F6.1 t/m F6.3 (SM-2 berekeningen) |
| O1.13 | Module: State Manager | JS | F9.1 t/m F9.3 (localStorage) |
| O1.14 | Module: Session Builder | JS | F5.1 t/m F5.3 (kaartselectie) |
| O1.15 | Module: Ring Renderer | JS | F4.1 t/m F4.3 (SVG ringen) |
| O1.16 | Module: Card Renderer | JS | F1.1 t/m F1.8 (kaartweergave) |
| O1.17 | Module: Block Manager | JS | F2.1 t/m F2.6 (blokvoortgang) |
| O1.18 | Module: Confetti | JS | F8.4 (particle-systeem) |
| O2 | `verbes_icon.png` | Asset | F8.2 (groen icoon) |

---

## Traceerbaarheidsmatrix

| SyR | Functie(s) | Component(en) | Verificatiemethode | Status |
|-----|-----------|---------------|-------------------|--------|
| SyR-1.1 | F1.1 | O1.6, O1.16 | Inspectie | ✅ Geverifieerd |
| SyR-1.2 | F1.2 | O1.6, O1.16 | Inspectie | ✅ Geverifieerd |
| SyR-1.3 | F1.1.1 | O1.6, O1.16 | Test | ✅ Geverifieerd |
| SyR-1.4 | F1.1.2 | O1.6, O1.16 | Test | ⏳ Nog te testen |
| SyR-1.5 | F1.1.3 | O1.6, O1.16 | Test | ⏳ Nog te testen |
| SyR-1.6 | F1.4 | O1.6, O1.16 | Inspectie | ✅ Geverifieerd |
| SyR-1.7 | F1.3 | O1.6, O1.16 | Inspectie | ✅ Geverifieerd |
| SyR-1.8 | F1.5 | O1.6, O1.4 | Inspectie | ✅ Geverifieerd |
| SyR-1.9 | F1.6 | O1.6, O1.4 | Inspectie | ⏳ Nog te testen |
| SyR-2.1 | F2.1 | O1.17, O1.2 | Inspectie | ✅ Geverifieerd |
| SyR-2.2 | F2.2 | O1.17 | Inspectie | ✅ Geverifieerd |
| SyR-2.3 | F2.3 | O1.17 | Test | ✅ Geverifieerd |
| SyR-2.4 | F2.4 | O1.8 | Test | ⏳ Nog te testen |
| SyR-2.5 | F2.5 | O1.5, O1.15 | Inspectie | ✅ Geverifieerd |
| SyR-2.6 | F2.6 | O1.17 | Test | ⏳ Nog te testen |
| SyR-3.1 | F3.1 | O1.2 | Tel | ✅ 38 werkwoorden |
| SyR-3.2 | F3.2 | O1.2 | Tel | ✅ 10 tijden |
| SyR-3.3 | F3.3 | O1.2 | Tel | ✅ Geverifieerd |
| SyR-3.4 | F3.4 | O1.2, O1.16 | Test | ⏳ Nog te testen |
| SyR-3.5 | F3.5 | O1.2, O1.16 | Test | ⏳ Nog te testen |
| SyR-4.1 | F4.1, F4.2 | O1.5, O1.15 | Inspectie | ✅ Geverifieerd |
| SyR-4.2 | F4.3 | O1.15 | Inspectie | ✅ Geverifieerd |
| SyR-4.3 | — | O1.5 | Inspectie | ✅ Geverifieerd |
| SyR-4.4 | F4.4 | O1.5 | Inspectie | ✅ Geverifieerd |
| SyR-5.1 | F5.1 | O1.14 | Tel | ⏳ Nog te testen |
| SyR-5.2 | — | O1.14 | Inspectie | ✅ Geverifieerd |
| SyR-5.3 | F5.2 | O1.14 | Test | ⏳ Nog te testen |
| SyR-6.1 | F6.1 | O1.12 | Inspectie | ✅ Geverifieerd |
| SyR-6.2 | F6.2 | O1.12 | Test | ✅ Geverifieerd |
| SyR-6.3 | F5.3 | O1.14 | Test | ⏳ Nog te testen |
| SyR-7.1 | F7.1 | O1.9, O1.3 | Inspectie | ✅ Geverifieerd |
| SyR-7.2 | F7.2 | O1.9 | Test | ✅ Geverifieerd |
| SyR-8.1 | F8.1 | O1.1 | Inspectie | ✅ Geverifieerd |
| SyR-8.2 | F8.2 | O2 | Inspectie | ✅ Geverifieerd |
| SyR-8.3 | F8.3 | O1 | Inspectie | ✅ Geverifieerd |
| SyR-8.4 | F8.4 | O1.7, O1.11, O1.18 | Test | ⏳ Nog te testen |
| SyR-8.5 | — | O1.6 | Inspectie | ✅ Geverifieerd |
| SyR-8.6 | — | O1.17 | Test | ✅ Geverifieerd |
| SyR-8.7 | F8.5 | O1.1 | Inspectie | ✅ Geverifieerd |
| SyR-9.1 | F9.1 | O1.13 | Test | ✅ Geverifieerd |
| SyR-9.2 | F9.2 | O1.13, O1.10 | Test | ⏳ Nog te testen |
| SyR-9.3 | F9.3 | O1.13, O1.10 | Test | ⏳ Nog te testen |
| SyR-9.4 | F9.4 | O1.10 | Inspectie | ✅ Geverifieerd |
| SyR-9.5 | — | O1 | Inspectie | ✅ Geverifieerd |
| SyR-10.1 | F1.9 | O1.6, O1.16 | Test | ✅ Geverifieerd |
| SyR-10.2 | F1.9 | O1.6, O1.16 | Inspectie | ✅ Geverifieerd |
| SyR-10.3 | F1.2 | O1.6, O1.16 | Test | ✅ Geverifieerd |
| SyR-11.1 | F3.1 | O1.2 | Inspectie | ✅ Geverifieerd |

---

## Datastructuur — Werkwoord-object

```javascript
{
  inf: 'parler',                    // infinitief
  nl: 'spreken',                    // Nederlandse vertaling
  type: 'regular-er',              // regular-er | regular-ir | regular-re | auxiliary | irregular | spelling | reflexive | impersonal
  block: 2,                        // hoofdblok (1-8)
  sub: 1,                          // sub-blok binnen hoofdblok
  spellingNote: null,              // of: 'voor -a/-o behoudt manger zijn -e-'
  spellingHighlight: null,         // of: { 'nous': [4,5] } (character indices to highlight)
  reflexive: false,                // wederkerend?
  tenses: {
    present: {
      je: 'parle', tu: 'parles', il: 'parle',
      nous: 'parlons', vous: 'parlez', ils: 'parlent',
      example: { fr: 'Tu parles français très bien.', nl: 'Jij spreekt heel goed Frans.' },
      rule: 'Présent -er: stam + -e, -es, -e, -ons, -ez, -ent'
    },
    passeCompose: { /* idem met hulpww */ },
    imparfait: { /* ... */ },
    // etc.
  }
}
```

## State-structuur — localStorage

```javascript
{
  progress: {
    currentBlock: 0,              // actief hoofdblok (0-7)
    currentSub: 0,                // actief sub-blok
    blockTestPassed: [false, ...] // per hoofdblok: toets gehaald?
  },
  cards: {
    'parler|present|2': {         // key = infinitief|tijd|personIdx (0-5)
      ease: 2.5,
      interval: 0,
      due: 1778916707456,         // timestamp (ms)
      reps: 0,
      lapses: 0,
      streak: 0,
      phaseProgress: 0,           // per-kaart fase (0-5): 0-1=FR→NL, 2-3=NL→FR, 4-5=mix
      lastSeen: null
    }
  },
  sessionStats: {
    recentRatios: []              // laatste 4 sessie-scores
  }
}
```

---

## Vervallen / niet meer relevant
- ~~Swipe-interactie~~ → vervangen door multiple choice (intake vraag 1)
- ~~Drie dagelijkse sessies tracking~~ → vrij oefenen gekozen (intake vraag 8)
- ~~Tekstuele voortgangsindicator~~ → alleen visuele ringen (intake vraag 10)
- ~~Hint-knop~~ → niet gewenst (intake vraag 12)
- ~~Placement test~~ → iedereen begint bij blok 1 (intake vraag 14)
- ~~Passé simple productie~~ → alleen herkenning (intake vraag 22)

# Sprint 2 — Upload instructies

**Wat je gaat uploaden:** de nieuwe `dashboard.html` met ingebouwde drawing tools voor proefsleuven + boringen.

---

## Wat er nieuw is in Sprint 2

### Drawing tools
- **Proefsleuven intekenen** — klik polygoon-hoekpunten op de kaart, dubbelklik om af te sluiten
- **Boringen plaatsen** — klik op locatie, popup voor invoer (ID, diepte, type)
- **8 onderzoek-soorten** bij proefsleuven (Kruisingsdetectie, Archeologisch proefvak, etc.)
- **7 boring-types** (Handboring, CPT, Peilbuis, Kernboring, etc.)

### Export & Import
- **Export GeoJSON** — alle intekeningen naar GIS-formaat
- **Export CSV** — Excel-friendly (met UTF-8 BOM, puntkomma-separator)
- **Import GeoJSON** — laad eerder geëxporteerde survey terug

### UX verbeteringen
- **Live counter** — toont aantal proefsleuven + boringen in de toolbar
- **Hint-panel** tijdens tekenen met instructies + Esc om te annuleren
- **Session-persistence** — intekeningen blijven bewaard tijdens sessie
- **Custom markers** met pulse-animatie voor boringen
- **Legenda uitgebreid** met proefsleuf + boring symbolen
- **Pulse-animatie** op actieve tekenknop

### Technisch
- Leaflet-draw 1.0.4 toegevoegd (CDN)
- RD New (EPSG:28992) wordt automatisch omgezet naar WGS84
- Geen externe API-calls — alle data blijft lokaal
- Geen localStorage nodig (werkt ook in privacy-modi)

---

## Upload stappen (5 minuten)

### Stap 1 — Vervang dashboard.html

1. Ga naar https://github.com/GaborMisic/IWR-procesnavigator
2. Klik op **`dashboard.html`** in de bestandslijst
3. Klik op het **✏️ potlood-icoon** rechtsboven
4. Selecteer alle inhoud (`Ctrl+A`) → verwijder
5. Open lokaal `outputs/dashboard.html` → kopieer alle inhoud
6. Plak in GitHub editor
7. Scroll naar beneden → **Commit changes**
   - Commit message: `Sprint 2: proefsleuven + boringen drawing tools`
   - Klik groene knop

### Stap 2 — Update CHANGELOG.md

1. Klik op `CHANGELOG.md` in de repo
2. Klik potloodje
3. Voeg onderaan (of onder `## v10.0`) deze sectie toe:

```markdown
## v10.1 (april 2026) — Sprint 2: Drawing tools

### 🆕 Nieuw
- **Proefsleuven intekenen** op tracékaart via polygoon-tekengereedschap
- **Boringen plaatsen** als point-markers met formulier voor diepte/type/opmerking
- **8 onderzoek-categorieën** voor proefsleuven (Kruisingsdetectie, Archeologisch, Bodemkundig, etc.)
- **7 boring-types** (Handboring, CPT, Peilbuis, Kernboring, Puur, Mechanische boring)
- **Export naar GeoJSON** voor GIS-gebruik
- **Export naar CSV** met UTF-8 BOM + puntkomma-separator (opent direct in NL-Excel)
- **Import GeoJSON** voor roundtrip-workflow
- **Live counter** in toolbar toont aantal ingetekende objecten
- **Animated hint-panel** tijdens tekenen met instructies + Esc-cancel

### ✨ Verbeterd
- Legenda uitgebreid met proefsleuf + boring symbolen
- Leaflet-draw controls gestyled in editorial-thema
- Custom boring-marker met pulse-effect en dashed-ring decoratie
- Session-persistence: intekeningen blijven bewaard bij tab-switch

### 🔧 Technisch
- Leaflet-draw 1.0.4 toegevoegd via CDN
- Alle data blijft lokaal — geen externe API-calls
- Werkt in privacy-modus (geen localStorage vereist)
```

4. Commit: `Update CHANGELOG voor Sprint 2`

### Stap 3 — Test live

1. Wacht 2-3 minuten tot GitHub Pages is herbouwd
2. Open https://gabormisic.github.io/IWR-procesnavigator/dashboard.html
3. Klik tab **🗺 Tracékaart**
4. Test:
   - Klik **▱ Proefsleuf tekenen** → teken polygon → vul formulier
   - Klik **● Boring plaatsen** → klik locatie → vul formulier
   - Klik **⬇ Export CSV** → CSV opent in Excel
   - Klik **⬆ Import survey** → laad CSV/GeoJSON terug

---

## Wat je kunt testen

### Scenario 1 — Proefsleuf tekenen
1. Zoom naar Maasstraat (Dordrecht)
2. Klik **Proefsleuf tekenen**
3. Klik 4 hoekpunten, dubbelklik om af te sluiten
4. Popup opent: vul naam "PS-Noord", diepte "1.5", onderzoek "Kruisingsdetectie"
5. Klik **✓ Opslaan**
6. Counter toont: `1 proefsleuven · 0 boringen`

### Scenario 2 — Boring + Export
1. Klik **Boring plaatsen**
2. Klik een locatie naast de proefsleuf
3. Popup: vul ID "B-01", diepte "3.0", type "Handboring"
4. Opslaan
5. Klik **⬇ Export GeoJSON** → `survey_<timestamp>.geojson` download
6. Klik **⬇ Export CSV** → `survey_<timestamp>.csv` → open in Excel

### Scenario 3 — Roundtrip
1. Teken 2 proefsleuven + 3 boringen
2. Export GeoJSON
3. Klik **✕ Wissen** → alles weg
4. Klik **⬆ Import survey** → kies het GeoJSON
5. Alles komt terug, inclusief metadata

---

## Volgende (Sprint 3 — later)

Mogelijke uitbreidingen als dit werkt:
- [ ] Koppeling survey-coördinaten aan Excel-rijen (vlookup bij project-ID)
- [ ] DXF-export voor AutoCAD
- [ ] Meetlint-tool (distance measurement)
- [ ] Afmeting/oppervlakte weergave bij proefsleuven
- [ ] Screenshot/PDF export van kaart+survey

Laat weten hoe Sprint 2 bevalt.

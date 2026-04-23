# GitHub Upload — Stap-voor-stap instructies

**Doel:** alle Sprint 1 bestanden uploaden naar je repo via GitHub web interface. Geen git-kennis nodig.

---

## Wat je gaat uploaden

Vanuit de `outputs/github/` map:

1. **`README.md`** → vervangt bestaande (hoofdpagina van repo)
2. **`INSTALLATIEGIDS.md`** → nieuw
3. **`FAQ.md`** → nieuw
4. **`CHANGELOG.md`** → nieuw

Vanuit `outputs/`:

5. **`IWR_Procesnavigator_TEMPLATE_v10_master.xlsm`** → in `assets/` map

---

## Stappen

### Stap 1 — Ga naar je repo
Open in je browser:  
https://github.com/GaborMisic/IWR-procesnavigator

### Stap 2 — Upload README.md (vervangen)

1. Klik op **`README.md`** in de bestandslijst
2. Klik op het **✏️ potlood-icoon** rechtsboven (Edit this file)
3. Selecteer alle inhoud (`Ctrl+A`) → verwijder
4. Open `outputs/github/README.md` lokaal → kopieer alle inhoud
5. Plak in de GitHub editor
6. Scroll naar beneden → **Commit changes**
   - Commit message: `Update README — v10 release`
   - Klik groene knop **Commit changes**

### Stap 3 — Upload nieuwe docs (INSTALLATIEGIDS, FAQ, CHANGELOG)

1. Ga terug naar de repo-hoofdpagina
2. Klik **Add file** (rechtsboven, naast groene "Code" knop) → **Upload files**
3. Sleep deze 3 bestanden tegelijk:
   - `INSTALLATIEGIDS.md`
   - `FAQ.md`
   - `CHANGELOG.md`
4. Onder "Commit changes":
   - Commit message: `Add installatiegids, FAQ en changelog`
5. Klik **Commit changes**

### Stap 4 — Upload de nieuwe Excel template

1. Ga terug naar de repo-hoofdpagina
2. Klik op de map **`assets`** (dubbelklik om te openen)
3. Klik **Add file** → **Upload files**
4. Sleep: `IWR_Procesnavigator_TEMPLATE_v10_master.xlsm`
5. Commit message: `v10 master template — VBA + cascade dropdowns + 4 stappenplan`
6. Klik **Commit changes**

### Stap 5 — Controleer

Open in browser:
- https://github.com/GaborMisic/IWR-procesnavigator → nieuwe README zichtbaar?
- https://github.com/GaborMisic/IWR-procesnavigator/blob/main/INSTALLATIEGIDS.md → opent?
- https://gabormisic.github.io/IWR-procesnavigator/ → live site geüpdatet? (kan 2-5 min duren)

---

## Na de upload

**Download-link werkt?**  
Test zelf: https://github.com/GaborMisic/IWR-procesnavigator/raw/main/assets/IWR_Procesnavigator_TEMPLATE_v10_master.xlsm

Download moet direct starten.

**GitHub Pages build klaar?**  
Check: https://github.com/GaborMisic/IWR-procesnavigator/deployments → laatste deployment moet ✅ zijn

---

## Volgende sprint

Zodra deze upload compleet is, starten we Sprint 2:
- Drawing tools toevoegen (proefsleuven + boringen)
- Dashboard.html uitbreiden
- Export functies

Laat het weten wanneer upload klaar is.

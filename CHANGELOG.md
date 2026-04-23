# Changelog — IWR Procesnavigator

Alle noemenswaardige wijzigingen per versie.

---

## v10.0 (april 2026) — Master template

### 🆕 Nieuw
- **Start_Hier** compleet herschreven als visueel 4-stappen stappenplan
- **AutoFilter** actief op Dashboard_Engineer — filter per project, status, eigenaar
- **Help-ballonnen** op elke kolomkop in Dashboard_Engineer (hover voor uitleg)
- **Cascade dropdowns** volledig herbouwd — A-Conditionerend → Aanvullend toont nu Natura 2000 stikstof, vergunning en Wet Natuurbescherming
- **4 demo-projecten** ingevoegd: Maasstraat (Dordrecht), Rozensingel (Capelle), Honingerdijk (Rotterdam), Molenstraat (Strijen)
- **Onderbouwingstabel** in Help-blad voor buffer-waarden (contractueel vs dashboardafleiding)

### ✨ Verbeterd
- **Rustiger Dashboard_Engineer**: 16 kolommen verborgen (Norm_Wd, Buffer_Wd, Gate_Ref, ItemID, berekende datums, audit-trail)
- **Route + Variant verborgen** — constant per project, hoeft niet per rij zichtbaar
- **Professionele terminologie** — alle Trinitas-interne taal verwijderd uit zichtbare velden
- **Projectoverzicht** heeft nu rode waarschuwingsbalk voor projecten met >5 weken slip

### 🔧 Technisch
- **VBA** (auto-datumstempel) geborgd via her-injectie bij elke template-update
- **Status → `Ingediend` / `Afgerond`** triggert automatische datumstempeling
- **Audit trail**: Laatst_Gewijzigd + Gewijzigd_Door (Environ USERNAME) bij elke wijziging
- **0 formule-fouten** verifieerbaar via `recalc.py` script

### 🌐 Web
- **Tracékaart** toegevoegd als vierde tab in dashboard.html
- Leaflet.js met PDOK basemaps (OSM, Luchtfoto, BGT)
- DXF + KML + GeoJSON parser voor tracé-uploads
- RD New (EPSG:28992) → WGS84 auto-conversie

---

## v9.0 (eerder)

### Nieuw
- Basis template met 11 bladen
- IWR-contract v2.1 doorlooptijden geïmplementeerd
- Trinitas-praktijktijden overgenomen
- VBA voor automatische datum-stempeling (beta)

---

## Roadmap — v11 (sprint 2, mei 2026)

### Geplant
- [ ] **Proefsleuven intekenen** op tracékaart (Leaflet-draw polygonen)
- [ ] **Boringen intekenen** als point-layer met popup-formulier
- [ ] **Export naar GeoJSON + CSV** — voor import in Excel
- [ ] **Sync-indicator** — wanneer Excel en kaart laatst gesynchroniseerd
- [ ] **API-stub** voor toekomstige backend-integratie (Node/Python)

### In onderzoek
- AutoCAD DWG → begroting-input extractor
- BGT-integratie voor automatische bodemtype-analyse
- Multi-user collaboration via SharePoint/cloud

---

## Versiebeheer

Versies volgen [Semantic Versioning](https://semver.org/):
- **Major** (v10 → v11): Nieuwe functies, mogelijk breaking changes
- **Minor** (v10.0 → v10.1): Nieuwe functies, backwards compatible
- **Patch** (v10.0.0 → v10.0.1): Bugfixes

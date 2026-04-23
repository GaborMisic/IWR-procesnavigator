# IWR Procesnavigator

**Planningstool voor Infrawerk Rijnmond — SoRSoZ (Stedin / Evides)**

Voorspelt wanneer een infrastructuurproject werkelijk klaar kan zijn met engineering, en welke taak op het kritieke pad zit. Gebaseerd op het **IWR-contract v2.1** en **Trinitas doorlooptijden**.

---

## 🌐 Live

- **Landing page:** https://gabormisic.github.io/IWR-procesnavigator/
- **Interactief dashboard:** https://gabormisic.github.io/IWR-procesnavigator/dashboard.html

## 📥 Download Excel tool

**Nieuwste versie (v10):**  
[📘 IWR_Procesnavigator_TEMPLATE_v10_master.xlsm](assets/IWR_Procesnavigator_TEMPLATE_v10_master.xlsm)

Bevat: VBA-automatisering, cascade-dropdowns, ingebouwde help, 4 demo-projecten (Maasstraat, Rozensingel, Honingerdijk, Molenstraat).

Zie [INSTALLATIEGIDS.md](INSTALLATIEGIDS.md) voor de eerste stappen.

---

## Wat doet deze tool?

| Probleem | Oplossing |
|---|---|
| Wanneer is mijn project echt klaar voor GSU? | Model berekent **voorspelde GSU** op basis van actuele status van alle onderzoeken + engineering-gates |
| Welk onderzoek ligt op het kritieke pad? | **Stoplicht-logica** markeert items die GSU in gevaar brengen |
| Halen we de contractuele doorlooptijden? | Vergelijkt **werkelijke voortgang** tegen **IWR-normen + Trinitas-praktijktijden** |
| Wie is verantwoordelijk? | **Eigenaar per item**: Netbeheerder, Aannemer, Engineer, Grondzaken Stedin |
| Hoe log ik vertragingen transparant? | **Oorzaakcode + toelichting** per showstopper |

---

## Voor wie?

- **Project managers** infrawerk (Heijmans, andere IWR-aannemers)
- **Engineers** die tracés voorbereiden (VO → DO → vergunningen)
- **Opdrachtgevers** (Stedin, Evides) die transparantie willen
- **Planners** die tegelijk op meerdere projecten werken

---

## Kernfunctionaliteiten

### 📋 Procesgestuurde planning
- 52 onderzoek- en engineering-items per project
- 4 routes (Netgedreven, Klantgedreven, Reconstructie) × 2 varianten (OidK, NOidK)
- Contractuele gates: Initiatie → VO → Proefsleuven → DO → Vergunning → Begroting → Materiaal → GSU

### ⚡ Automatische datum-stempeling
- Status → `Ingediend` stempelt Datum_Uitgezet
- Status → `Afgerond` / `Goedgekeurd` stempelt Datum_Ontvangen
- Audit-trail: wie wijzigde wat, wanneer

### 🗺️ Interactieve tracékaart
- Leaflet.js + PDOK basemaps (OpenStreetMap, Luchtfoto, BGT)
- Project-pins met GSU-status-kleuren
- Upload GeoJSON / DXF / KML tracés
- *(Binnenkort: proefsleuven + boringen intekenen)*

### 📊 GSU-prognose per project
- Verwachte GSU vs originele GSU
- Delta in werkdagen + week-weergave
- Rood (>5 wk slip) / Oranje (krap) / Groen (binnen planning)

### 📈 Projectoverzicht
- Alle projecten in één oogopslag
- Kritieke items per project
- Percentage afgerond

---

## Technische basis

| Laag | Stack |
|---|---|
| **Excel-model** | openpyxl + VBA (auto-datumstempel, audit trail) |
| **Kaartvisualisatie** | Leaflet.js + PDOK WMTS |
| **Formules** | Excel native — WORKDAY, INDEX/MATCH, cascade-dropdowns |
| **Hosting** | GitHub Pages (gratis, publiek) |

---

## Licentie en contact

Deze tool is gebouwd voor IWR Infrawerk Rijnmond.  
Voor vragen, feedback of samenwerking: open een [issue](https://github.com/GaborMisic/IWR-procesnavigator/issues).

---

**v10.0** (april 2026) — zie [CHANGELOG.md](CHANGELOG.md)

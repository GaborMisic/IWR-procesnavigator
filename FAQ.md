# Veelgestelde vragen — IWR Procesnavigator

## Algemeen

### Wat is de IWR Procesnavigator?
Een Excel-tool + webdashboard dat de procesmatige doorlooptijd van infrastructuurprojecten onder het IWR-contract voorspelt. Combineert contractuele normen (IWR v2.1) met praktijktijden (Trinitas).

### Voor welke contracten werkt dit?
Ontworpen voor **Infrawerk Rijnmond (SoRSoZ)** — Stedin + Evides. De structuur is toepasbaar op andere IWR-regio's door alleen de normtijden en projectgegevens aan te passen.

### Is dit een vervanger van FSM?
**Nee.** FSM is operationeel (werkorders in uitvoering). Deze tool is voor **engineering-voorbereiding** (planning vóór uitvoering start). Complementair.

---

## VBA en macro's

### De datum wordt niet automatisch gestempeld bij "Ingediend"
Mogelijke oorzaken in volgorde van waarschijnlijkheid:

1. **Macro's niet ingeschakeld** → klik "Inhoud inschakelen" (gele balk bij openen)
2. **AutoSave staat aan op SharePoint** → zet AutoSave uit linksboven
3. **Bestand is een `.xlsx` i.p.v. `.xlsm`** → download opnieuw
4. **`Application.EnableEvents` staat op False** → Alt+F11 → Ctrl+G → typ `Application.EnableEvents = True` → Enter
5. **Code staat in verkeerde plek** → moet in `ThisWorkbook`, niet in `Module1`

### Ik krijg geen gele balk "Inhoud inschakelen"
- Ga naar: `Bestand → Opties → Vertrouwenscentrum → Instellingen → Macro-instellingen`
- Kies: **"Alle macro's inschakelen met melding"**
- Herstart Excel

### Werkt de tool op Mac?
Deels. VBA-automatisering werkt, maar sommige Excel-functies (WORKDAY.INTL) gedragen zich anders. Test grondig voor productie-gebruik.

### Werkt de tool in Excel Online?
**Nee.** VBA wordt niet ondersteund in Excel Online. Gebruik Excel desktop (Windows) voor volledige functionaliteit.

---

## Invoeren en bewerken

### Hoe voeg ik een nieuw project toe?
1. Ga naar blad **Projecten**
2. Voeg een rij toe onderaan
3. Vul minimaal: ProjectID, Projectnaam, Route, Variant, GSU-datum, Engineer
4. Ga naar **Dashboard_Engineer** en kies je ProjectID uit de dropdown

### Hoe verwijder ik een project?
1. Verwijder alle rijen met dat ProjectID uit **Dashboard_Engineer**
2. Verwijder de rij uit **Projecten**
3. Alle berekeningen vallen automatisch weg

### Hoe wijzig ik de GSU-datum?
Alleen in het **Projecten** blad. Alle andere bladen (Dashboard_Engineer, Projectoverzicht, Sleuteldata) schuiven automatisch mee.

### Hoe voeg ik meerdere onderzoeken tegelijk toe?
Werk direct in Dashboard_Engineer. Voor elk item kies je via cascade-dropdowns (Hoofdcategorie → Subcategorie → Type). Het model vult automatisch Norm, Buffer, Vereiste_Gereed in.

### Waarom zijn sommige kolommen verborgen?
Die kolommen (Norm_Wd, Buffer_Wd, Gate_Ref etc.) bevatten **berekeningen** die niet handmatig ingevoerd hoeven worden. Als je ze wilt zien: rechtsklik op een kolomletter → **Verbergen opheffen**.

---

## Berekeningen en data

### Waar komen de doorlooptijden vandaan?
- **Contractuele normen:** IWR-contract v2.1, bijlage Doorlooptijden
- **Praktijktijden:** Trinitas planning-template (Evides/Stedin gebruiken deze al in hun werkvoorbereiding)

Beide zijn inzichtelijk in het blad **Normtijden_Config**.

### Wat is het verschil tussen Norm_Wd en Buffer_Wd?
- **Norm_Wd** = hoe lang een item duurt (doorlooptijd in werkdagen)
- **Buffer_Wd** = hoe lang voor GSU het klaar moet zijn (contractuele offset)

Voorbeeld: Warme overdracht (2.O.3) heeft Buffer_Wd = -185 wd = 37 weken voor GSU.

### Waarom staat Buffer_Wd -185 voor warme overdracht?
Dit is een dashboard-afleiding. Het IWR-contract stuurt op een tijdlijn in **weken**: -37 weken voor GSU. In het dashboard wordt dit omgerekend naar werkdagen: -37 × 5 = -185 wd.

**Belangrijk:** 185 staat **niet letterlijk** in het contract. Zie blad `Route_Variant_Offsets` kolom K voor de status-onderbouwing per gate.

### Waarom toont Geimpliceerde_GSU soms 01-01-1900?
Dit betekent dat de berekening niet uitgevoerd kan worden — meestal:
- GSU-datum ontbreekt in Projecten blad
- Status = "N.v.t." (dit item is niet van toepassing)
- Datum_Uitgezet mist terwijl Status = "Ingediend"

### Waarom verschilt de vertraging per item zoveel?
Elk item hangt aan een **andere contractuele gate**. Voorbeeld:
- **Bodemonderzoek NG-OidK** → hangt aan warme overdracht (2.O.3) → moet klaar **37 wk** voor GSU
- **Natura 2000 oriëntatie** → hangt aan VO-einde (2.O.11) → moet pas klaar **18 wk** voor GSU

Dus ook al is Natura 2000 oriëntatie sneller (5 wd vs 20 wd), het heeft meer marge omdat de deadline later is.

---

## Tracékaart en web

### Wat doet de web-dashboard?
Toont projecten op een kaart met PDOK basemaps (OpenStreetMap, Luchtfoto, BGT). Project-pins kleuren op basis van GSU-status.

### Kan ik proefsleuven en boringen intekenen?
**Binnenkort.** Sprint 2 (mei 2026) voegt drawing tools toe aan het dashboard: polygonen voor proefsleuven, points voor boringen, met export naar GeoJSON/CSV.

### Hoe laad ik mijn eigen tracé?
In dashboard.html, tab *🗺 Tracékaart*:
- Upload een **GeoJSON**, **KML**, of **DXF** bestand
- RD New coördinaten (EPSG:28992) worden automatisch geconverteerd naar WGS84

### Kan ik data uit BDOK (Antea Group) laden?
Ja. Export je BDOK-project als GeoJSON vanaf bdok.nl, upload in de tracékaart.

---

## Beveiliging en privacy

### Zijn mijn projectgegevens veilig op GitHub?
De **tool zelf** staat publiek op GitHub. Jouw **projectgegevens** staan in je lokale Excel-bestand — die zijn **niet** gedeeld. Je data blijft bij jou.

### Kan ik de tool op SharePoint gebruiken?
Ja, maar:
- Zet **AutoSave uit** (anders blokkeert VBA)
- Voeg SharePoint toe als **Vertrouwde locatie**
- Werk 1 persoon tegelijk (geen co-authoring — dat breekt VBA)

---

## Nog een vraag?

Open een [issue](https://github.com/GaborMisic/IWR-procesnavigator/issues) of neem contact op met Gabor Misic.

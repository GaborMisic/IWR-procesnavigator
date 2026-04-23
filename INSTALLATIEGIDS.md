# Installatiegids — IWR Procesnavigator v10

Deze gids helpt je om de tool binnen 15 minuten werkend te krijgen, inclusief VBA-automatisering.

---

## 1. Download de template

Klik op de downloadlink:  
👉 [IWR_Procesnavigator_TEMPLATE_v10_master.xlsm](assets/IWR_Procesnavigator_TEMPLATE_v10_master.xlsm)

Sla op in een lokale map, bijvoorbeeld:  
`C:\Projecten\IWR_Procesnavigator\`

**Niet** opslaan in `Downloads` — Windows blokkeert dan macro's standaard.

---

## 2. Blokkering opheffen (Windows)

Bestanden uit internet krijgen een "Mark of the Web" — daardoor blokkeert Excel de macro's.

1. Rechtsklik op het bestand in Verkenner
2. Kies **Eigenschappen**
3. Onderaan het tabblad *Algemeen* staat mogelijk:  
   *"Dit bestand is afkomstig van een andere computer..."*
4. Vink **"Blokkering opheffen"** aan
5. Klik **OK**

---

## 3. Open het bestand

1. Dubbelklik op het `.xlsm` bestand
2. Excel toont mogelijk een gele balk: **"Inhoud inschakelen"** → klik erop
3. Als de balk niet verschijnt: zie Troubleshooting hieronder

---

## 4. Controleer macro-instellingen

Als er **geen** gele balk verschijnt:

1. **Bestand** → **Opties** → **Vertrouwenscentrum**
2. Klik **Instellingen Vertrouwenscentrum**
3. **Instellingen voor macro's**
4. Kies: **"Alle macro's inschakelen met meldingen"**
5. OK → sluit Excel → open bestand opnieuw

---

## 5. Eerste gebruik — test in 3 stappen

### Test 1: VBA werkt
1. Ga naar het blad **Dashboard_Engineer**
2. Zoek een rij met Status = `Nodig`
3. Wijzig naar `Ingediend`
4. ✅ Datum_Uitgezet vult automatisch in met vandaag

Werkt niet? Zie [FAQ.md](FAQ.md) → *"VBA stempelt geen datum"*

### Test 2: Cascade dropdowns werken
1. In Dashboard_Engineer, klik een lege cel in kolom **Hoofdcategorie**
2. Kies bijv. `A-Conditionerend`
3. Klik cel rechts → **Subcategorie** → kies `Aanvullend`
4. Klik cel rechts → **Type** → je ziet nu:
   - Natura 2000 — stikstofberekening
   - Natura 2000 — vergunningprocedure
   - Veldonderzoek archeologie
   - Wet Natuurbescherming

Werkt niet? Check of macros zijn ingeschakeld.

### Test 3: GSU-prognose schuift mee
1. Ga naar blad **Projecten**
2. Wijzig GSU-datum van een project (bijv. Maasstraat van 18-01-2027 naar 15-02-2027)
3. Ga terug naar **Projectoverzicht**
4. ✅ GSU_Verwacht, Delta, en stoplichten zijn bijgewerkt

---

## 6. Je eerste eigen project

1. **Projecten** blad → voeg een rij toe:
   - ProjectID (bijv. `IRN26-0123`)
   - Projectnaam
   - Stad
   - Route (Netgedreven / Klantgedreven / Reconstructie)
   - Variant (NOidK / OidK)
   - GSU-datum
   - Engineer-naam

2. **Dashboard_Engineer** blad → voeg rijen toe:
   - Kies je ProjectID in kolom A
   - Kolommen B-C-F-G worden automatisch ingevuld (Projectnaam, GSU, Route, Variant)
   - Kies Hoofdcategorie → Subcategorie → Type uit de dropdowns
   - Vul Eigenaar + Status in
   - Datum_Uitgezet stempelt automatisch bij Status = `Ingediend`

3. **Projectoverzicht** toont direct je GSU-prognose

---

## Troubleshooting

### Geen gele balk + VBA werkt niet
- Check: bestand in vertrouwde map (niet `Downloads`)
- Check: blokkering opgeheven (stap 2)
- Check: macro-instelling op "Met meldingen" (stap 4)
- Check: bestand is `.xlsm` (niet `.xlsx`)

### AutoSave blokkeert VBA op SharePoint
- AutoSave **uit** zetten linksboven
- Handmatig opslaan met `Ctrl+S`
- Of: SharePoint-locatie toevoegen als **Vertrouwde locatie**

### Cascade dropdown toont niets
- Controleer kolom F (Hoofdcategorie) is ingevuld
- Controleer kolom G (Subcategorie) is ingevuld
- Dropdown in H (Type) werkt alleen als F én G zijn gekozen

### Berekening toont 01-01-1900
- Meestal: GSU-datum ontbreekt voor dit project
- Ga naar Projecten blad en vul GSU-datum in

---

## Support

Meer vragen? Zie [FAQ.md](FAQ.md) of open een [issue](https://github.com/GaborMisic/IWR-procesnavigator/issues).

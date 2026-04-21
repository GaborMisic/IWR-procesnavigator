# IWR Procesnavigator v10 — Wat is nieuw en hoe te gebruiken

## Wat v10 toevoegt t.o.v. v9

### 1. Cascading dropdowns (fix bug dat D-Boring + Quickscan mogelijk was)

De dropdowns in Dashboard_Engineer werken nu cascade:
- **Hoofdcategorie** (A-Conditionerend / B-Bodem / … / H-Gate)
- **Subcategorie** toont alléén wat relevant is bij de gekozen Hoofdcategorie
- **Type** toont alléén wat relevant is bij de gekozen (Hoofdcategorie + Subcategorie)
- **ItemID** wordt automatisch afgeleid (lookup)

Voorbeeld: kies A-Conditionerend → Subcategorie toont {Quickscan, Vervolg, Aanvullend}.
Kies D-Boring → Subcategorie toont {Haalbaarheid, Plan, Engineering, Sondering, Vergunning}. Géén Quickscan.

**Werkwijze in Excel**: klik op een cel in kolom Hoofdcategorie → dropdown verschijnt. Kies. Klik dan in kolom Subcategorie → de dropdown past zich aan. Klik in kolom Type → idem.

### 2. Voorspelbaarheid: GSU_Verwacht

Nieuwe kolom **Geimpliceerde_GSU** in Dashboard_Engineer:
```
Geimpliceerde_GSU = WORKDAY(Verwacht_Gereed_Datum, +Buffer_Wd)
```
Dit is de vroegst haalbare GSU die dit specifieke item toestaat.

Nieuw blad **Projectoverzicht**: toont per project:
- **GSU_Oorspronkelijk** (uit Projecten)
- **GSU_Verwacht** = MAX van alle Geimpliceerde_GSU waardes per project
- **Delta_Werkdagen** / **Delta_Weken** (slip)
- **Status** stoplicht (op koers / krap / slip)
- **Kritiek_Item** — welke taak zorgt voor de slip

**Verwacht_Gereed_Datum** is verbeterd: voor items met Status="Nodig" (nog niet uitgezet) rekent het model nu: `WORKDAY(TODAY(), Norm_Doorlooptijd_Wd)`. Dus je ziet de vroegst haalbare datum ook als niemand de taak al uitgezet heeft.

### 3. Route-specifieke Types zijn nu uniek

Items die per route/variant een andere doorlooptijd hebben, staan nu met route in de naam:
- "Bodemonderzoek CROW 400 — NG-OidK 2.O.8 (20wd)"
- "Bodemonderzoek CROW 400 — RC-NOidK (10wd)"
- "Proefsleuven 2.NO.4 — KG-NOidK (10wd)" / "— NG-NOidK (50wd)" / "— RC-NOidK (20wd)"
- "Onderzoeken Tracé 2.O.9 — NG-OidK (75wd)" / "— RC-OidK (35wd)"
- "DO-dossier goedgekeurd — KG (5wd)" / "— NG (15wd)" / "— RC (15wd)"
- "Warme overdracht — NG-OidK (-37wk)" / "— RC-OidK (-29wk)"

Engineer kiest dus expliciet de juiste variant voor zijn project.

### 4. Maasstraat (IRN24-0175) als voorbeeldproject

Geladen met de stand per 7-apr-2026 uit `Kopie_van_Planning_NG_-_07-04-2026.xlsx`:
- Route: Netgedreven OidK, GSU gepland 11-jan-2027
- Warme overdracht afgerond (8-apr-2026)
- Bodemonderzoek ingediend op 10-apr-2026
- Aanvullend: Natura 2000 tool + Historisch bodem + Tracéonderzoek + VO + DO + Vergunningen + Begroting + Kick-off allemaal als "Nodig"

Het model voorspelt GSU_Verwacht = 22-jan-2027 (slip van 9 werkdagen) met als kritiek item het Bodemonderzoek. Aanvullend OO en Quickscan ecologie zitten ruim binnen het venster. Les: bodemonderzoek 2 weken eerder uitzetten zou GSU weer ruim haalbaar maken.

## Gebruik — de voorspelde GSU uitlezen

1. Ga naar blad **Projectoverzicht**.
2. Zoek je project op in kolom ProjectID.
3. Lees in kolom **GSU_Verwacht** de voorspelde datum.
4. Kolom **Delta_Werkdagen** toont hoeveel dagen afwijking van de oorspronkelijke GSU.
5. Kolom **Kritiek_Item** toont wélke taak de slip veroorzaakt — dat is je interventiepunt.
6. Voor gedetailleerde rijen: ga terug naar **Dashboard_Engineer** en filter op die ProjectID.

## VBA-installatie (optioneel, voor datum-stempeling)

Zie `README_conversie_naar_xlsm.md` en `dashboard_vba.bas` uit v9 — die werken ongewijzigd op v10. De VBA stempelt Datum_Uitgezet bij Status→Ingediend, Datum_Ontvangen bij Status→Afgerond/Goedgekeurd, en houdt Laatst_Gewijzigd/Gewijzigd_Door bij.

Let op: kolomindex is in v10 verschoven omdat Geimpliceerde_GSU is toegevoegd. Pas de constanten in dashboard_vba.bas aan:

```vba
Private Const COL_LaatstGewijzigd    As Long = 31   ' was 30 in v9
Private Const COL_GewijzigdDoor      As Long = 32   ' was 31 in v9
```

## Bladoverzicht

1. Start_Hier — intro + uitleg
2. Projecten — projectenmaster (blauw = invoer)
3. Dashboard_Engineer — werkblad per afhankelijkheid per project
4. Projectoverzicht — ⭐ voorspelde GSU per project
5. Vertragingen_Showstoppers — automatisch afgeleide lijst
6. Sleuteldata — 13 mijlpaaldatums per project
7. Normtijden_Config — bibliotheek (52 rijen)
8. Route_Variant_Offsets — gate offsets (72 rijen)
9. Procesregister — IWR-contract referentie
10. _Lijsten / _Keuzes — dropdownbronnen (verborgen)
11. Help — uitleg + bekende inconsistenties

## Bronnen

- IWR-contract v2.1 (9 PDFs)
- Trinitas `Planning_Trinitas_Evides_Stedin_-_basis_met_behoud_dropdowns.xlsm`
- Planning NG `Kopie_van_Planning_NG_-_07-04-2026.xlsx` (voor Maasstraat-data)

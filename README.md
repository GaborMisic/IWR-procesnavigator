# IWR Procesnavigator

Planningstool voor Infrawerk Rijnmond (SoRSoZ · Stedin / Evides) — voorspelt wanneer een project werkelijk klaar kan zijn met engineering en welke taak op het kritieke pad zit, op basis van het **IWR-contract v2.1** en **Trinitas-doorlooptijden**.

🌐 **Live**: https://gabormisic.github.io/IWR-procesnavigator/
📊 **Dashboard**: https://gabormisic.github.io/IWR-procesnavigator/dashboard.html
📥 **Download Excel-tool**: [assets/IWR_Procesnavigator_v10.xlsx](assets/IWR_Procesnavigator_v10.xlsx)

## Wat doet deze tool

1. **Afhankelijkheden bewaken** — per project één rij per onderzoek, vergunning, boring, proefgat, verkeersplan, schouw of gate.
2. **GSU-voorspelling** — per taak een "geïmpliceerde GSU": de vroegst haalbare startdatum. Het projectoverzicht toont de MAX daarvan = de verwachte GSU per project.
3. **Kritiek pad aanwijzen** — welk item bepaalt de slip. Eén kolom, één interventiepunt.

## Structuur van deze repo

```
/
├── index.html                    — landing page
├── dashboard.html                — live web-dashboard
├── assets/
│   ├── style.css                 — styling
│   ├── demo-data.json            — Maasstraat + 3 voorbeeldprojecten
│   ├── IWR_Procesnavigator_v10.xlsx   — de Excel-tool
│   └── README_v10.md             — documentatie v10
└── README.md                     — dit bestand
```

## Technisch

- Volledig **statische site** — werkt op GitHub Pages zonder build-stap.
- Dashboard parseert xlsx in de browser via **SheetJS** (data blijft lokaal, nooit naar een server).
- Tailwind **niet** gebruikt — pure CSS met CSS-variabelen.
- Gebouwd met het IWR-contract v2.1 (9 PDFs) en Trinitas als bronnen.

## Versies

- **v10** (huidig) — cascading dropdowns, Geimpliceerde_GSU-kolom, Projectoverzicht met voorspelde GSU, Maasstraat als voorbeeldproject
- **v9** — eerste werkende consolidatie van IWR v8 en Trinitas
- **v8** — origineel enkel-project template

Zie [assets/README_v10.md](assets/README_v10.md) voor de volledige changelog.

## Werkwijze

1. Open **Projectoverzicht** op het dashboard of in het Excel-bestand
2. Zoek projecten met 🟠 of 🔴 status
3. Lees kolom **Kritiek_Item** — dat is de taak die eerder uitgezet moet
4. Ga naar **Dashboard_Engineer**, filter op dat ProjectID, pas Status aan
5. De voorspelling herberekent automatisch

## Contact

Gabor Misic — Heijmans N.V., Infrawerk Rijnmond

# spend-cube-peru

Spend cube and savings analysis of Peruvian public procurement data (Python, SQL, Power BI).

> **Status:** 🚧 In progress — Phase 0 (setup and scoping)

## Business question

**Where could Peruvian public entities save money through better sourcing?**

This project builds a *spend cube*, a classified view of purchasing by **supplier × category × buying entity × time**, and uses it to identify and size savings opportunities, the way a procurement team or consultant would at the start of a sourcing engagement.

## Scope

| Item | Decision |
| --- | --- |
| Data source | Public contracting data from OECE (formerly OSCE), published from SEACE |
| Period | 2024–2025 |
| Included | Goods and services contracts |
| Excluded | Works (construction), which are project-specific and not comparable |
| Sector lens | Categories that mirror mining and energy procurement: fuel, fleet and equipment maintenance, tires, security, industrial supplies |

## Approach

1. **Explore** – profile the raw data, confirm the grain (contract vs item), and establish total spend per year
2. **Clean** – filter to awarded contracts, standardize currency, handle outliers, and normalize supplier names using RUC plus fuzzy matching
3. **Classify** – map spend to a 2-level category taxonomy with keyword rules, then a text classifier for the long tail; validate accuracy on a hand-labeled sample
4. **Build the cube** – star schema (fact + supplier, entity, category, date dimensions) and a Power BI dashboard
5. **Find opportunities** – Pareto, fragmentation, price variance, competition, and supplier concentration (HHI) analyses
6. **Size savings** – quantify the top opportunities as ranges with stated assumptions

## Deliverables

- [ ] Clean, classified spend dataset
- [ ] Power BI dashboard
- [ ] Opportunity memo (5–6 slides) with quantified savings
- [ ] Documented, reproducible code

## Repository structure

```
spend-cube-peru/
├── data/            # raw and clean data (not tracked in Git)
│   ├── raw/
│   └── clean/
├── notebooks/       # numbered analysis notebooks (01_explore, 02_clean, ...)
├── src/             # reusable Python functions
├── reports/         # dashboard screenshots and the opportunity memo
├── decisions.md     # log of every cleaning and methodology decision
└── README.md
```

## Tools

Python (pandas, rapidfuzz, scikit-learn) · DuckDB (SQL) · Power BI · Git

## Data

Raw data is not stored in this repository. It can be downloaded from the OECE open data portal: [Portal de Datos Abiertos del OECE](https://www.gob.pe/14272-acceder-al-portal-de-datos-abiertos-del-oece).

## Results

*Coming soon.*

## Author

Sebastián Valdivia — Industrial Engineering, PUCP

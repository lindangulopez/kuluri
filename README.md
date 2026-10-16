# Kuluri

**Record once, share with control.**

Team 27 – Kuluri, [EU Agri-Hackathon 2026](https://agrihackathon.iservice-europa.eu/), Challenge 3 "Flowing data, empowered collaboration".

## Problem

Buyers and public administrations increasingly ask farmers to prove fair working conditions: buyers for their fair-trade and responsible-sourcing commitments, authorities because, since 2025, Common Agricultural Policy payments are linked to labour compliance (social conditionality). Farmers' labour records are scattered and hard to trust, so they repeat the same information for every buyer and authority.

## Direction

Kuluri turns everyday work into trustworthy evidence. Farmer and worker agree a deal (tasks, dates, pay). The farmer records the work, and the worker confirms it through their own link, in their own language. Buyers' requests and public-administration reports are filled in from that evidence, using only totals, never personal data. Mandatory compliance is always answered; beyond that, the farmer decides which buyer sees what.

## This weekend's prototype

| Screen | What it does |
| --- | --- |
| `app/farmer.py` | Create a deal, log days and hours |
| `app/worker.py` | Open a personal link, read the deal in your language, confirm or dispute |
| `app/report.py` | Pick a recipient, see the answers filled in from confirmed records, totals only |

`data/mapping_table.csv` links each piece of evidence to a buyer question and a legal requirement.

## Data

The prototype uses the **synthetic dataset** provided by the hackathon organisers (DG AGRI). It has labour per holding only, so `data/generate_workers.py` creates individual workers and daily logs whose totals match the dataset, and `data/reconcile.py` checks that they do. No real personal data is used anywhere. The dataset itself and its access details are **not** stored in this repository (`data/raw/` is ignored).

## Use of AI

Draft, to complete before submission: AI tools helped develop the solution (coding assistant; architecture diagrams made with [Archify](https://github.com/lindangulopez/archify)). Whether AI runs inside the product, what it does, and its limits will be stated here.

## Run

```bash
python -m venv .venv && source .venv/bin/activate
pip install -r requirements.txt
cp .env.example .env
streamlit run app/farmer.py
```

## Team

[@lindangulopez](https://github.com/lindangulopez) (Team Lead), [@juanzotes](https://github.com/juanzotes), [@ENZOMOTIVE](https://github.com/ENZOMOTIVE), Maria Filippou.

Project site, diagrams and deck: [kuluri-site](https://lindangulopez.github.io/kuluri-site/). Task board: GitHub Project "Kuluri, EU Agri-Hackathon".

## Licence

Code: [MIT](LICENSE). Documentation and diagrams in [kuluri-site](https://github.com/lindangulopez/kuluri-site): CC BY 4.0.

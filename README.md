# Bitcoin, Ether, and the Meme-Coin Rug-Pull Era

A data analysis of Bitcoin and Ether returns versus alternative cryptocurrencies and meme coins during the 2023-2024 cycle, with a focus on rug pulls in the meme-coin sector.

## Data

Monthly cryptocurrency price, market-capitalization, and rug-pull data scraped from Dune Analytics and DEXScreener. Rug-pull incident metadata cross-referenced against CertiK Skynet alerts and Chainalysis quarterly fraud reports.

The full dataset covers 36 months, January 2022 through December 2024, and is stored in `monthly_crypto.csv`.

## Files

- `scraper.py` — nightly scraper that pulls from Dune and DEXScreener and writes `monthly_crypto.csv`
- `queries/` — Dune Analytics SQL used by the scraper
- `monthly_crypto.csv` — monthly aggregates
- `analysis.ipynb` — main analysis notebook
- `findings.md` — quantitative findings summary
- `STORY.md` — long-form narrative

## Reproducing

```bash
pip install -r requirements.txt
python scraper.py        # refreshes monthly_crypto.csv
jupyter nbconvert --execute analysis.ipynb
```

Requires Python 3.9 or later. Tested on Python 3.11.

## Dependencies

- pandas
- numpy
- matplotlib
- requests
- duneanalytics

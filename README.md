# Stock Data Extraction & Visualization

Python notebooks that combine historical share prices with scraped quarterly revenue data for Tesla and GameStop. The workflow demonstrates API-based data collection, HTML parsing, data cleaning, and interactive visualization.

Developed around the IBM Skills Network stock-data assignment as part of data-analysis learning.

## Workflow

1. Retrieve historical prices with `yfinance`.
2. Download the assignment's revenue pages with `requests`.
3. Parse HTML tables with Beautiful Soup.
4. Clean currency symbols, separators, and empty revenue values using pandas.
5. Plot share price and revenue in a two-panel Plotly figure.

## Notebooks

| Notebook | Contents |
| --- | --- |
| [tesla_stock_prices.ipynb](tesla_stock_prices.ipynb) | Tesla revenue extraction, stock history, and plotting function. |
| [gamestop_stock_prices.ipynb](gamestop_stock_prices.ipynb) | GameStop revenue extraction, stock history, and plotting function. |
| [Final Assignment-v2.ipynb](Final%20Assignment-v2.ipynb) | Original assignment scaffold, including unfinished exercise cells. |

## Local setup

Use Python 3 and a Jupyter environment.

```bash
git clone https://github.com/stevenrashid/Web-Scraping.git
cd Web-Scraping
python -m venv .venv
```

Activate the environment, then install the notebook dependencies:

```bash
python -m pip install "pandas<3" yfinance requests beautifulsoup4 plotly nbformat jupyterlab
jupyter lab
```

Open a company notebook. In the GameStop notebook, execute the `def make_graph(...)` cell **before** the earlier `make_graph(gme_data, gme_revenue, 'GameStop')` call, or move that definition above the call.

## Reproducibility notes

- Network access is required to retrieve prices and revenue pages. Reruns may produce different price histories.
- The plotting function limits prices to June 14, 2021 and revenue to April 30, 2021.
- The notebooks use pandas' legacy `infer_datetime_format` argument; the setup above keeps pandas below version 3. Dependencies were not originally locked.
- Scraping relies on the assignment pages' table structure. If a source page changes, its table selection may need updating.

## Acknowledgments

The assignment scaffold and supplied graphing guidance originate from IBM Skills Network. Original notebook credits are retained.

# SpaceX Falcon 9 Landing Success Prediction

**IBM Data Science Professional Certificate — Applied Data Science Capstone**

## Overview

SpaceX advertises Falcon 9 launches at $62 million, compared to $165+ million from other providers — largely because SpaceX reuses the first stage instead of discarding it. If the first stage lands successfully, it can be refurbished and reflown, dramatically cutting cost.

This project asks: **can we predict whether the Falcon 9 first stage will land successfully, using historical launch data?** If landing success is predictable, launch cost becomes predictable too — useful for anyone (including a competitor) trying to estimate what a SpaceX launch actually costs.

## Project Workflow

1. **Data Collection** — `jupyter-labs-spacex-data-collection-api.ipynb`
   Collected Falcon 9 launch records via the SpaceX v4 REST API (rocket, launchpad, payload, and core details).

2. **Web Scraping** — `jupyter-labs-webscraping.ipynb`
   Scraped the Falcon 9 launch history table from Wikipedia as a second, cross-checked data source.

3. **Data Wrangling** — `labs-jupyter-spacex-Data_wrangling.ipynb`
   Cleaned and merged the datasets; engineered the binary `Class` label (1 = successful landing, 0 = unsuccessful) from the mission outcome field.

4. **EDA with SQL** — `jupyter-labs-eda-sql-coursera_sqllite.ipynb`
   Queried the dataset to answer specific questions: unique launch sites, payload totals by booster, landing outcome counts, and more.

5. **EDA with Data Visualization** — `edadataviz.ipynb`
   Explored relationships between flight number, launch site, payload mass, orbit type, and landing outcome using scatter, bar, and line charts.

6. **Interactive Map (Folium)** — `lab_jupyter_launch_site_location.ipynb`
   Built an interactive map showing all four launch sites, color-coded launch outcomes, and calculated distances to the nearest coastline, highway, and town.

7. **Interactive Dashboard (Plotly Dash)** — `spacex-dash-app.py`
   Built a dashboard with a launch site dropdown, a success-rate pie chart, a payload range slider, and a payload-vs-outcome scatter chart.

8. **Predictive Analysis** — `SpaceX_Machine_Learning_Prediction_Part_5.ipynb`
   Trained and tuned four classifiers (Logistic Regression, SVM, Decision Tree, KNN) with `GridSearchCV`. The **Decision Tree** model performed best, reaching ~94% accuracy on held-out test data.

## Key Findings

- **KSC LC-39A** has both the most successful launches and the highest launch success rate among the four sites.
- Payload mass in the **2,500–5,000 kg** range has the most reliable high success rate; **5,000–7,500 kg** underperforms.
- All launch sites are built close to the coastline (CCAFS SLC-40 sits under 1 km from it) — likely for safety, so failed-launch debris falls into the ocean rather than over land.
- The **Decision Tree classifier** was the most accurate model for predicting first-stage landing success.

## Tools & Libraries

Python, Pandas, NumPy, Requests, BeautifulSoup, SQLite, Matplotlib, Seaborn, Folium, Plotly Dash, scikit-learn

## Author

Zainab Jannat

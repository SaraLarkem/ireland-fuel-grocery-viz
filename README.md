# Exploring the Relationship Between Fuel and Grocery Prices in Ireland (2016–2026)

## Overview

Many Irish households have felt prices rise sharply in recent years, and fuel and food prices are often talked about together. This project uses official data from the Central Statistics Office (CSO) to look at how petrol and diesel prices are linked to food prices in Ireland from January 2016 to September 2026. We compare long-term trends, look at whether food prices tend to follow fuel prices after a delay, check how prices moved during major events (COVID-19, the Ukraine invasion, the ECB rate hikes and the 2026 Strait of Hormuz disruption), and compare fresh (perishable) and long-lasting (shelf-stable) groceries. The results show how the prices are linked and move together over time; they are not proof that one price changes the other.

**Live website:** https://saralarkem.github.io/ireland-fuel-grocery-viz/web/

An interactive one-page version of the findings, built with D3.js. It has charts you can hover over, a slider that lines up the diesel and food peaks, and a Present button for full-screen presenting.

## Team

| | |
|---|---|
| **Team members** | Ahlam Khalil, Chenrui Xie, Sara Larkem |
| **Module** | Data Visualisation 4 |
| **Lecturer** | Yuhang Ye |

## Research Questions

1. **Overall relationship:** How closely are changes in petrol and diesel prices linked to changes in food prices in Ireland?
2. **Time lag:** Do food prices tend to follow fuel prices straight away, or after a delay of several months?
3. **Major events:** How did fuel and food prices move during major events (COVID-19 lockdowns, post-COVID supply issues, the Ukraine invasion, the ECB rate hikes and the Strait of Hormuz disruption) compared with normal months?
4. **Perishable vs shelf-stable:** Did fresh groceries and long-lasting groceries rise in price by different amounts?

## Data Sources

| Source | What it contains | Period | Downloaded | Link |
|---|---|---|---|---|
| CSO table CPM24 | Consumer Price Index for petrol, diesel and food and non-alcoholic beverages (December 2023 = 100) | January 2016 – September 2026 | 12 October 2026 | https://data.cso.ie/table/CPM24 |
| CSO table CPM12 | National average prices of 14 grocery items, in euro | January 2016 – October 2026 | 21 November 2026 | https://data.cso.ie/table/CPM12 |

Both datasets are monthly and have no missing values. The grocery item data runs one month longer than the fuel data, so the analyses that combine them use January 2016 – September 2026.

## Repository Structure

| Folder | Contents |
|---|---|
| `data/` | Raw CSO downloads and the cleaned and processed CSV files made by the notebooks |
| `notebooks/` | Jupyter notebooks for data cleaning, analysis and the final charts (run in order 01 → 06) |
| `images/` | Charts saved by the notebooks (the presentation charts start with `final_`) |
| `docs/` | Project documents: topic pitch, proposal, team charter and stakeholder, audience and data audit |
| `web/` | The interactive website (`index.html`), published with GitHub Pages |

## Notebooks

| No. | File | What it does | Main output |
|---|---|---|---|
| 01 | `01_Data_Cleaning_Fuel_Groceries.ipynb` | Loads the raw CPM24 data, reshapes it so petrol, diesel and food each have their own column, converts the dates, and checks for missing values, gaps and duplicate months. | `data/cleaned_fuel_grocery_data.csv` |
| 01b | `01b_Data_Cleaning_Grocery_Items.ipynb` | Cleans the raw CPM12 prices for the 14 grocery items, converts the dates, and checks that every month has all 14 items. | `data/cleaned_grocery_subcategories.csv` |
| 02 | `02_Trend_Analysis.ipynb` | Calculates 3- and 12-month rolling averages and year-on-year % changes, and splits food prices into trend, seasonal pattern and leftover noise. | `data/02_trend_analysis_output.csv` |
| 03 | `03_External_Shocks_and_Event_Impact.ipynb` | Compares monthly price changes (average, largest and volatility) in six event periods with normal months. | Event charts in `images/` (e.g. `price_volatility_by_period.png`) |
| 04 | `04_Grocery_Subcategory_Disaggregation.ipynb` | Splits the 14 items into perishable and shelf-stable groups (7 each), turns each into an index (January 2016 = 100), and compares both groups with fuel prices. | `data/04_grocery_groups_output.csv` |
| 05 | `05_Correlation_and_Lag_Analysis.ipynb` | Measures the correlation between fuel and food price changes at lags of 0–18 months, fits a simple regression at the strongest lag, and checks the result with and without 2021–2023. | `images/correlation_vs_lag_fuel_and_food.png` |
| 06 | `06_Final_Visualizations.ipynb` | Turns the results into 5 presentation-ready charts for a general audience, with a design card for each chart and the main message. | `images/final_1_...png` to `images/final_5_...png` |

## Key Findings

**Main message:** In Ireland, food price inflation tended to follow fuel price inflation by about 9–12 months, mainly during the 2021–23 price surge, and food prices stayed high after fuel prices fell.

1. **The big picture:** Fuel prices spiked twice: petrol peaked at 125.5 in June 2022 and diesel reached its highest level, 126.2, in April 2026 (December 2023 = 100). Food prices rose more slowly, by at most 13.1% in a year (compared with up to 50.8% for diesel), and by September 2026 they were 28.5% above their lowest point in January 2021, close to their highest level.
2. **Fuel swings, food doesn't:** In normal months, petrol and diesel moved about 1.5–1.7% a month, food about 0.3%. During the Ukraine invasion, petrol moved 7.6% a month (5.0 times normal) and diesel 6.8% (4.0 times normal), while food moved 1.1% a month.
3. **The delay, shown directly:** Diesel price inflation peaked at +50.8% in June 2022. Food price inflation peaked 10 months later at +13.1% in April 2023, after staying at about +13.1% from February 2023 (8–10 months after the diesel peak).
4. **Correlation vs lag:** Year-on-year food inflation is most closely linked to diesel inflation 10 months earlier (r = 0.61) and to petrol inflation 12 months earlier (r = 0.59). Without 2021–2023, the diesel correlation at 9–12 months is negative (−0.31 to −0.42).
5. **Which groceries rose most:** From January 2016 to September 2026, perishable groceries rose by 34.6% and shelf-stable groceries by 14.6%, a rise 2.4 times larger for perishable items.

## Limitations

- **The lag pattern mostly comes from 2021–2023.** When those years are left out, the link between fuel and food inflation disappears, so the 9–12 month delay is not a stable rule that holds at all times.
- **Correlation does not prove cause.** Fuel and food prices are linked, but other costs (wages, energy for processing and refrigeration, packaging, world prices for milk and grain, the euro) also rose in the same period.
- **The grocery groups are only 7 items each.** They are simple averages, not weighted like the official CPI, and one item can move a group a lot (jam fell by about 20%). The split into perishable and shelf-stable is our own decision.
- **National averages only.** The data does not show differences between regions, shops or brands.
- **The 2026 period is short.** The Strait of Hormuz disruption has only 2 months of data and the period after it only 5, so it is too early to say whether food prices will follow the 2026 fuel price jump.

## How to Run

1. Clone the repository and open the folder in VS Code (with the Python and Jupyter extensions), or open the notebooks in Google Colab.
2. Install the Python packages:
   ```
   pip install pandas numpy matplotlib seaborn statsmodels
   ```
   (`statsmodels` is only needed for the seasonal decomposition in Notebook 02. Colab already has all of these.)
3. Run the notebooks in order: **01 → 01b → 02 → 03 → 04 → 05 → 06**. Use "Restart and Run All" for each one.

Notes:
- Notebooks 01, 02, 03, 04 and 05 load their input files from this repository on GitHub, so they need an internet connection. Notebooks 01b and 06 load from the local `data/` folder.
- The notebooks save their CSV files to `data/` and their charts to `images/`. This works whether you run them from the `notebooks/` folder (VS Code) or from the repository root.
- In Colab, clone the repository first (`!git clone https://github.com/SaraLarkem/ireland-fuel-grocery-viz.git` then `%cd ireland-fuel-grocery-viz`) so that the `data/` folder is available to Notebooks 01b and 06.

## Use of AI Tools

The team used Claude and ChatGPT for bug fixing, light research, chart design suggestions, code review and creating this README. All AI suggestions were checked by the team before they were used, and all numbers in the notebooks are calculated from the CSO data. The full record of how AI was used and what we decided is in the AI Decision Log, a Word document in the [`docs/`](docs/) folder.

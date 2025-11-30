# Climate Impact on Coffee Futures Prices

## Overview
This project explores the relationship between weather conditions in Brazil’s top two coffee-producing regions — Minas Gerais and São Paulo — and the Coffee C Futures prices traded on the New York Intercontinental Exchange (ICE). Coffee production in these regions is highly sensitive to climate variability, particularly changes in temperature, rainfall, and frost events. The aim is to understand how regional climate patterns translate into price fluctuations in the international coffee futures market.

The study uses historical Coffee C Futures data (ticker `KC=F`) collected via the `yfinance` Python library and meteorological data from the Open-Meteo API for the period 2010–2025. The dataset will include monthly averages of temperature, precipitation, and frost-related variables. Both direct and lagged (1–3 month) effects of weather anomalies on futures prices will be analyzed to capture the delayed influence of climate stress on production and market response.

Finally, the project will apply machine learning models to forecast future coffee futures prices based on climatic indicators. Model performance will be evaluated using metrics such as RMSE and R². By linking environmental and financial data, this project aims to demonstrate how climate risk in Brazil’s agricultural sector can predict and explain volatility in global coffee futures markets.

## Data Sources
The dataset covers the period from **January 2010 to January 2025**.
* **Coffee Prices:** Historical Coffee C Futures data retrieved via the `yfinance` library.
* **Weather Data:** Monthly average temperature and precipitation data for Minas Gerais and São Paulo retrieved via the **Open-Meteo API**.

## Project Structure
* `dsa210_project.ipynb`: The main Jupyter Notebook containing data collection, cleaning, visualization, and hypothesis testing codes.
* `coffee_climate_data.csv`: The processed dataset merging financial and meteorological data.
* `requirements.txt`: List of Python libraries required to run the project.

## Methodology
1.  **Data Collection:** Automated Python scripts were used to fetch financial and meteorological data.
2.  **Data Cleaning:** Data was resampled to monthly frequencies to align weather patterns with price closing dates. Missing values were handled to ensure consistency.
3.  **Exploratory Data Analysis (EDA):** Visualized price trends, seasonal weather patterns, and correlation matrices using Matplotlib and Seaborn.
4.  **Hypothesis Testing:**
    * **Lagged Correlation:** Investigated if rainfall has a delayed effect (2 months) on prices using Pearson correlation.
    * **T-Test:** Compared average coffee prices during "drought" periods (lowest 25% precipitation) vs. normal periods.

## Findings
The statistical analysis yielded the following insights:

* **Drought Impact:** The analysis showed that coffee prices tend to be higher during drier months.
    * Average Price during Drought Months: **$171.63**
    * Average Price during Normal Months: **$157.90**
    * *Interpretation:* While there is a visible price difference (~$14 increase during droughts), the T-test p-value (**0.13**) indicates that this difference is not statistically significant at the 95% confidence level. This suggests that while weather plays a role, other market factors also heavily influence prices.

* **Lagged Correlation:** No strong linear correlation was found between monthly rainfall and prices with a 2-month lag (Pearson r: **0.06**). This implies that the relationship is likely non-linear or driven by extreme events rather than monthly averages.

## Limitations & Future Work
* **Time Aggregation:** Using monthly averages smoothens out extreme daily weather events (like sudden frost) which often cause immediate price spikes.
* **Market Complexity:** Futures prices are influenced by global supply chains, currency exchange rates (BRL/USD), and speculation, not just local weather.
* **Future Plan:** Integrating daily frost data and expanding the region scope could improve the analysis.

## How to Run
1.  Install the required dependencies:
    ```bash
    pip install -r requirements.txt
    ```
2.  Run the Jupyter Notebook:
    ```bash
    jupyter notebook dsa210_project.ipynb
    ```

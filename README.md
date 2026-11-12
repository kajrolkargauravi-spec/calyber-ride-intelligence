# CALYBER — Fair Pricing Intelligence for Mumbai Ride-Hailing

Calyber is a ride-hailing fare and pricing fairness exploration project focused on Mumbai. It analyses a dataset of **54,132 trip records** and provides an interactive Streamlit application for examining fare patterns, surge pricing, rider vulnerability, and a proposed fairer pricing policy.

The application brings together fare forecasting, fairness indicators, trip scenario comparisons, and exploratory analytics to help users understand how factors such as time, weather, vehicle type, and rider circumstances can affect estimated trip costs.

> **Note:** Calyber is an analytical and demonstration project, not a live connection to a ride-hailing provider. Forecasts and policy comparisons are based on the assumptions and calculations implemented in this repository. They should not be interpreted as live market quotes or verified platform prices.

## Project Goals

- Explore how ride-hailing fares and surge multipliers vary across trip conditions.
- Highlight pricing patterns for riders with fewer alternatives.
- Provide fare, wait-time, and cancellation-risk estimates for user-selected scenarios.
- Compare current scenario estimates with a proposed fairness-aware policy.
- Present the analysis through an accessible interactive dashboard.

## Features

### Predict
- Fare forecast across upcoming time intervals.
- Fairness score based on estimated surge and rider-vulnerability category.
- Estimated wait time.
- Estimated cancellation risk.
- Surge timing analysis.
- Fare anomaly check against the project's expected-fare calculation.

### Decide
- Vehicle recommendation based on trip distance and selected priorities.
- What-if analysis for alternative trip conditions.

### Compare
- Route and fare comparison.
- Scenario and policy comparison to explore the effect of a fairness-aware pricing approach.

### Explore
- Summary metrics and trip-level data exploration.
- Analysis by weather, demand, and rider-vulnerability groups.

## Dataset

The project includes prepared CSV files used by the dashboard:

- `pbi_trips.csv` — trip-level records used for the main analysis.
- `pbi_captive.csv` — summary metrics by rider-vulnerability quartile.
- `pbi_demand.csv` — demand summaries by day and hour.
- `pbi_kpi.csv` — dashboard KPI values.
- `pbi_weather.csv` — summary metrics by weather condition.
- `surge_patterns.csv` — hourly surge patterns by weather condition.

The trip dataset contains **54,132 records**. Review and document the original data source, collection method, and whether the records are synthetic or anonymised before publishing or reusing the data.

## Methodology and Interpretation

Calyber combines historical-pattern exploration with scenario calculations and a proposed policy simulation. The application code contains explicit fare-rate, time-of-day, weather, and rider-vulnerability assumptions.

A serialized demand-model artifact (`demand_model.pkl`) is included and loaded by the application. The current fare and scenario functions in `predictions.py` use the project's defined calculation rules; do not interpret every displayed estimate as a direct output from the serialized model.

The fairness indicators and policy comparisons are analytical measures defined for this project. They are not official regulatory standards or proof of discriminatory conduct by any specific ride-hailing company.

## Technology Stack

- Python
- Streamlit
- Pandas
- NumPy
- Scikit-learn
- Plotly
- Pickle for model serialization
- HTML/CSS for dashboard styling

## Repository Structure

```text
Calyber/
├── app.py
├── components.py
├── predictions.py
├── styles.css
├── demand_model.pkl
├── pbi_trips.csv
├── pbi_captive.csv
├── pbi_demand.csv
├── pbi_kpi.csv
├── pbi_weather.csv
├── surge_patterns.csv
├── requirements.txt
├── README.md
├── .gitignore
└── .streamlit/
    └── config.toml
```

## Run Locally

Python 3.12 is recommended.

### 1. Clone the repository

```bash
git clone https://github.com/YOUR-USERNAME/calyber.git
cd calyber
```

### 2. Create a virtual environment

**Windows (PowerShell):**

```powershell
python -m venv .venv
.venv\Scripts\Activate.ps1
```

**macOS / Linux:**

```bash
python3 -m venv .venv
source .venv/bin/activate
```

### 3. Install dependencies

```bash
python -m pip install --upgrade pip
pip install -r requirements.txt
```

### 4. Run the application

```bash
streamlit run app.py
```

The application will normally be available at `http://localhost:8501`.

## Deploy on Streamlit Community Cloud

1. Push this repository to GitHub.
2. Open Streamlit Community Cloud and sign in with GitHub.
3. Create a new app and select this repository and branch.
4. Set the main file path to `app.py`.
5. Select Python 3.12 in the app's advanced settings.
6. Deploy the application.

Keep the CSV files, `demand_model.pkl`, `predictions.py`, `components.py`, `styles.css`, and `.streamlit/config.toml` in the repository because the application depends on them.

## Limitations

- Results depend on the supplied dataset and the assumptions encoded in the application.
- Estimated fares, wait times, and cancellation risks are scenario estimates, not live provider data.
- The fairness score is a project-defined indicator and should not be treated as an official fairness certification.
- The quality and generalisability of conclusions depend on the dataset's provenance, coverage, and representativeness.
- The serialized model's training details and evaluation metrics should be documented separately if they are available.

## Author

**Gauravi Kajrolkar**

Data Science | Machine Learning | Analytics

- LinkedIn: https://www.linkedin.com/in/gauravi-k-976669313
- GitHub: https://github.com/YOUR-USERNAME

## Acknowledgement

Developed as a design-thinking and analytical project exploring ride-hailing fare transparency and pricing fairness in Mumbai.

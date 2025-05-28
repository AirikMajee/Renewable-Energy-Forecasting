# 🔋 Renewable Energy Forecasting using Weather & Grid Data

This project aims to forecast renewable energy generation in *India* using open-source weather data and national power grid reports. Inspired by platforms like *Electricity Maps, it integrates VRE (Variable Renewable Energy) generation with daily weather metrics to build an intelligent, city-aware **hourly energy model*.

---

## 📌 Motivation

India’s energy landscape is shifting massively toward renewables — yet *accurate forecasting* at a granular level remains a challenge. This project explores:

- 📈 Can we model solar and wind generation using just weather data?
- 🌤 Can city-specific forecasts be built using regional sunlight and wind patterns?
- 🔌 How can such forecasts help optimize grid stability, energy trading, and planning?

---

## 🗂 Data Sources

| Data Type       | Source                | Frequency | Description                                 |
|-----------------|-----------------------|-----------|---------------------------------------------|
| *VRE Reports*  | POSOCO REMC (PDF)     | Daily     | Wind & Solar summaries + REMC profiles       |
| *PSP Reports*  | POSOCO (Excel)        | Daily     | Statewise/sourcewise demand, forecast        |
| *NPP Reports*  | CEA (Excel)           | Daily     | Unit, Station & Sector-wise generation       |
| *Weather Data* | Open-Meteo API        | Daily     | Radiation, wind speed, temperature           |
| *City Mapping* | Manually Mapped       | Static    | Used for sunlight modeling (via Astral)      |

---

## ⚙ What We Did

### 🧩 *Part 1 – Data Collection, Preprocessing & Merging*

- 📥 Extracted and cleaned data from *1000+ PDFs and Excel files*
- 📊 Merged VRE, PSP, and weather datasets *aligned by date*
- 🧠 Engineered a solar model using shortwave_radiation_sum + panel efficiency
- 💨 Estimated wind power using daily wind speed + simplified turbine curve
- 🕘 Converted daily data into *hourly estimates* using irradiance and wind profiles
- 🔁 Combined city-level forecasts with regional VRE to simulate India-wide readiness

---

### 🛠 *Part 2 – Feature Engineering & Modeling*

- 🌇 Used Astral to compute *dynamic sunrise/sunset* times per city and date
- ⚡ Calibrated CUF using actual generation vs forecast deviation
- 🛰 Integrated live weather APIs for *real-time predictions*

---

### 📊 *Part 3 – Visualization & Deployment (Planned)*

- 🧪 Build an interactive *web dashboard* (like Electricity Maps)
- 🤖 Explore ML models (e.g., XGBoost, LSTM) for forecast learning
- 📈 Estimate forecast accuracy (MAPE, RMSE, etc.) across regions

---

## 📁 Folder Structure

```plaintext
renewable-energy-forecasting/
├── data/
│   ├── raw/           # POSOCO & weather files
│   ├── cleaned/       # Cleaned, dated reports
│   ├── final/         # Fully merged + modeled datasets
│   └── sample/        # Small test samples
├── notebooks/         # Jupyter Notebooks per phase
├── scripts/           # PDF parsing, merging, modeling
├── assets/            # Charts, screenshots, graphs
├── README.md          # This file
├── requirements.txt   # Python dependencies
└── .gitignore         # File exclusions 
```
---

**💡 Tech Stack**

pandas, numpy, matplotlib

astral – for sunlight modeling

PyMuPDF (fitz) – PDF parsing

glob, os, re – file automation

Open-Meteo API – historical weather data

---

**📈 Sample Output**

Sample graphs and dashboards will be uploaded in the assets/ folder.

---

**📜 License**

This project is licensed under the MIT License.

---

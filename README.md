# Renewable-Energy-Forecasting
**🔋Renewable Energy Forecasting using Weather & Grid Data**

This project aims to forecast renewable energy generation in India using open-source weather data and national power grid reports. Inspired by platforms like Electricity Maps, it integrates VRE (Variable Renewable Energy) generation data with daily weather metrics to build an intelligent, city-aware hourly energy model.

------------------------------------------------------------------------------------------------------------

**📌 Motivation**

India’s energy landscape is undergoing a massive shift toward renewable sources — yet forecasting clean energy availability at a granular level remains a challenge. This project explores:

📈 Can we model solar and wind generation using just weather data?

🌤 Can city-specific forecasts be built using regional sunlight and wind patterns?
🔌 How can such forecasts help optimize grid stability, energy trading, and planning?

---------------------------------------------------------------------------------------------------------------

**📁 Data Sources Used**

Data Type	Source	Frequency	Notes

VRE Reports	POSOCO REMC (PDF)	Daily	Wind & Solar summary + REMC profile
PSP Reports	POSOCO (Excel)	Daily	Statewise/sourcewise demand, forecast
NPP Reports	CEA (Excel)	Daily	Generation by unit, station & sector
Weather Data	Open-Meteo API	Daily	Radiation, wind speed, temperature
City Mapping	Manually Mapped Coordinates	Static	Used for sunlight modeling via Astral

----------------------------------------------------------------------------------------------------------------

**⚙ What We Did (PART 1 - DATA COLLECTION, PREPROCESSING & MERGING)**

📥 Extracted and cleaned data from 1000+ PDF and XLS files

📊 Built merged datasets aligning VRE, PSP and Weather sources by date

🧠 Engineered a solar model using shortwave_radiation_sum + panel efficiency

💨 Estimated wind power using daily wind speed + simplified turbine curve

🕘 Expanded daily VRE data to hourly using irradiance and wind profiles

🔁 Combined city-level forecasts with region-level VRE to simulate India-wide grid readiness

**⚙ What We Did (PART 2 - FEATURE ENGINEERING AND MOEDELLING)**

🌇 Use Astral to compute dynamic sunrise/sunset hours per city & date

⚡ Calibrate models using actual CUF, forecast vs actual deviation

🛰 Integrate with live weather APIs for real-time predictions

**⚙ What We Did (PART 3 - VISUALIZATION & DEPLOYMENT)**

🧪 Build an interactive web dashboard (like Electricity Maps)

🤖 Explore ML models (e.g. XGBoost, LSTM) to learn from weather + PSP deviations

📌 Estimate forecast accuracy region-wise, using error metrics like MAPE, RMSE

-------------------------------------------------------------------------------

**🔍 Folder Structure**

renewable-energy-forecasting/
├── data/
│   ├── raw/          # POSOCO & weather files
│   ├── cleaned/      # Cleaned, dated reports
│   ├── final/        # Fully merged + engineered datasets
├── notebooks/        # Jupyter notebooks for each phase
├── scripts/          # Extraction, parsing, modeling code
├── assets/           # Charts, screenshots, graphs
├── README.md         # This file
├── requirements.txt  # Python dependencies
└── .gitignore

---

**💡 Tech Stack**

pandas, numpy, matplotlib

astral (sunlight modeling)

PyMuPDF (fitz) for PDF parsing

glob, os, re for file automation

Open-Meteo API for historical weather data

---

**📈 Sample Output**

> Plots and dashboards will be uploaded in the assets/ folder.

---

**📜 License**

This project is licensed under the MIT License.

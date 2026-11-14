# 🛰️ Mangarita — NASA POWER Climate Explorer

**Mangarita** is a lightweight, interactive web application built in Python that transforms real satellite and meteorological data from the **NASA POWER API** into global climate comparisons, statistical trend analyses, and mathematical future projections—designed to work seamlessly both online and offline.

## ✨ Key Features

* **100% Real NASA POWER Data:** Downloads monthly historical records (from 2021 to the present) across 6 key atmospheric and solar variables:
  * Atmospheric Temperature (`T2M`, °C)
  * Relative Humidity at 2 m (`RH2M`, %)
  * Wind Speed at 10 m (`WS10M`, m/s)
  * Surface Pressure (`PS`, kPa)
  * Precipitation Rate (`PRECTOTCORR`, mm/day)
  * All-Sky Surface Shortwave Downward Irradiance (`ALLSKY_SFC_SW_DWN`, W/m²)
* **Resilient Local Reserve (`reserva_nasa.json`):** Automatically caches queried locations to disk. If there is no internet connection or the NASA API does not respond, **Mangarita never fabricates data**—instead, it uses the **Haversine formula** to locate and display the nearest verified station in the local reserve.
* **Global Comparison Dashboard:** Contrasts opposite climate zones (Arctic, Equatorial, Mediterranean, and Southern Hemisphere) and determines whether observed changes are statistically significant using a **Student's t-test**.
* **Dual Mathematical Projection Engine:**
  * **Server-Side Deep Projection (*"See the future"*):** Fits a linear trend plus seasonal harmonic cycles via least squares, displaying an approximate **95% prediction interval** while respecting real physical limits (e.g., humidity bounded between 0% and 100%).
  * **In-Browser Instant Projection (*"Predict future years"*):** Computes a 36-month projection directly in JavaScript with no internet connection or server calls required.

## 🚀 How to Run the Project

1. **Install the required dependencies:**
   ```bash
   pip install pandas numpy plotly requests
   ```

2. **Run the application:**
   ```bash
   python mangaritaaaa.py
   ```
   The local server will start automatically and open the application in your browser at `http://127.0.0`.

### Additional Terminal Options
* `python mangaritaaaa.py --no-download` — Starts immediately using only the data already saved in `reserva_nasa.json`.
* `python mangaritaaaa.py --update` — Refreshes all catalog locations with the latest available months in NASA POWER.

---
Made by **Samuel José Gordillo Mantilla** from Popayán, Colombia :)


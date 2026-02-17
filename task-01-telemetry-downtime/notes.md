# Task 01 – Telemetry Downtime Analysis (Tableau)

## Background
Daikibo collected machine telemetry from **4 factories** over **May 2021**.  
Each factory has **9 device types**, sending a message every **10 minutes**.  
Goal: identify **(1) which factory had the most breakdown time** and **(2) which device type broke most in that factory**.

Factories:
- Daikibo Factory Meiyo (Tokyo, Japan)
- Daikibo Factory Seiko (Osaka, Japan)
- Daikibo Berlin (Berlin, Germany)
- Daikibo Shenzhen (Shenzhen, China)

## Method (Tableau)
1. Imported the unified telemetry JSON dataset into Tableau.
2. Created a calculated field to estimate downtime:

   **Calculated Field: Unhealthy**
   - If status = "unhealthy" → **10**
   - Else → **0**
   - Interpretation: each unhealthy message represents **10 minutes** of potential downtime since the previous reading.

3. Built two bar charts:
   - **Down Time per Factory** (SUM of Unhealthy by Factory)
   - **Down Time per Device Type** (SUM of Unhealthy by Device Type)

4. Created a dashboard and set **Down Time per Factory** as a filter so selecting a factory updates the device chart.

## Results
- **Factory with the most downtime:** `daikibo-factory-seiko`
- **Device type contributing the most downtime in that factory:** `LaserWelder`

## Deliverable
- Dashboard screenshot saved as:
  `downtime_dashboard.png`

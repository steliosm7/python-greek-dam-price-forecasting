##  Model Performance & Backtesting Analysis

The model's robustness was tested using a dynamic rolling-window validation approach. We evaluated the LightGBM algorithm across various training window sizes (150, 120, 90, 60, and 45 days) to assess the trade-off between capturing recent market dynamics and maintaining long-term structural trends.

### Overall Out-of-Sample Metrics


### Overall Out-of-Sample Metrics

| Metric | Out-of-Sample Value |
| :--- | :--- |
| **Out-of-Sample MAE** | 20.07 €/MWh |
| **Out-of-Sample RMSE** | 32.11 €/MWh |

### Detailed Error Analysis by Price Bin (Dynamic Blend)


| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count |
| :--- | :--- | :--- | 
| **(-inf, 0.0]** | 8.40 | 3734 |
| **(0.0, 35.0]** | 21.17 | 2281 | 
| **(35.0, 85.0]** | 25.04 | 2858 | 
| **(85.0, 115.0]** | 17.53 | 6383 | 
| **(115.0, 150.0]** | 17.48 | 7229 |
| **(150.0, 200.0]** | 24.02 | 4635 | 
| **(200.0, inf]** | 38.54 | 2352 | 

### Visualizing the Forecast (90-Day Rolling Window)

![Forecast vs Real DAM Price](dam_forecast_90day.png)

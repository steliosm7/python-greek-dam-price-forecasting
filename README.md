##  Model Performance & Backtesting Analysis

The model's robustness was tested using a dynamic rolling-window validation approach. We evaluated the LightGBM algorithm across various training window sizes (150, 120, 90, 60, and 45 days) to assess the trade-off between capturing recent market dynamics and maintaining long-term structural trends.

### Overall Out-of-Sample Metrics

The results indicate that larger training windows yield better generalization, minimizing both MAE and RMSE.

| Rolling Window | Out-of-Sample MAE (€/MWh) | Out-of-Sample RMSE (€/MWh) |
| :---: | :---: | :---: |
| **150 Days** | 19.00 | 28.27 |
| **120 Days** | 19.37 | 28.87 |
| **90 Days** | 19.56 | 29.09 |
| **60 Days** | 19.65 | 29.08 |
| **45 Days** | 20.25 | 29.74 |

### Visualizing the Forecast (150-Day Baseline)

---

###  Detailed Error Analysis by Price Bin

To understand the model's behavior under different market regimes (e.g., negative prices, normal operation, extreme spikes), we analyzed the error distribution across specific price bins for each rolling window. 

*Click to expand the details for each backtesting window:*

<details>
<summary><b> 150-Day Rolling Window (Optimal Baseline)</b></summary>
<br>

| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count | Avg Actual Price |
| :--- | :--- | :--- | :--- |
| **(-50.001, 0.0]** | 10.33 | 2122 | -1.46 |
| **(0.0, 0.05]** | 24.15 | 356 | 0.01 |
| **(0.05, 67.718]** | 31.38 | 1237 | 27.82 |
| **(67.718, 109.81]** | 26.38 | 1240 | 93.50 |
| **(109.81, 120.93]** | 16.61 | 1240 | 115.24 |
| **(120.93, 130.55]** | 13.50 | 1238 | 125.88 |
| **(130.55, 140.801]** | 12.83 | 1236 | 135.51 |
| **(140.801, 154.504]** | 13.53 | 1238 | 147.51 |
| **(154.504, 172.888]** | 17.47 | 1238 | 163.25 |
| **(172.888, 519.29]** | 33.64 | 1239 | 203.30 |

</details>

<details>
<summary><b> 120-Day Rolling Window</b></summary>
<br>

| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count | Avg Actual Price |
| :--- | :--- | :--- | :--- |
| **(-50.001, 0.0]** | 10.59 | 2122 | -1.46 |
| **(0.0, 0.05]** | 23.49 | 356 | 0.01 |
| **(0.05, 67.718]** | 31.63 | 1237 | 27.82 |
| **(67.718, 109.81]** | 27.64 | 1240 | 93.50 |
| **(109.81, 120.93]** | 17.34 | 1240 | 115.24 |
| **(120.93, 130.55]** | 14.00 | 1238 | 125.88 |
| **(130.55, 140.801]** | 13.30 | 1236 | 135.51 |
| **(140.801, 154.504]** | 13.60 | 1238 | 147.51 |
| **(154.504, 172.888]** | 17.67 | 1238 | 163.25 |
| **(172.888, 519.29]** | 33.53 | 1239 | 203.30 |

</details>

<details>
<summary><b> 90-Day Rolling Window</b></summary>
<br>

| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count | Avg Actual Price |
| :--- | :--- | :--- | :--- |
| **(-50.001, 0.0]** | 10.35 | 2122 | -1.46 |
| **(0.0, 0.05]** | 24.56 | 356 | 0.01 |
| **(0.05, 67.718]** | 31.82 | 1237 | 27.82 |
| **(67.718, 109.81]** | 28.23 | 1240 | 93.50 |
| **(109.81, 120.93]** | 17.59 | 1240 | 115.24 |
| **(120.93, 130.55]** | 14.51 | 1238 | 125.88 |
| **(130.55, 140.801]** | 13.66 | 1236 | 135.51 |
| **(140.801, 154.504]** | 13.32 | 1238 | 147.51 |
| **(154.504, 172.888]** | 17.34 | 1238 | 163.25 |
| **(172.888, 519.29]** | 34.25 | 1239 | 203.30 |

</details>

<details>
<summary><b> 60-Day Rolling Window</b></summary>
<br>

| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count | Avg Actual Price |
| :--- | :--- | :--- | :--- |
| **(-50.001, 0.0]** | 9.98 | 2122 | -1.46 |
| **(0.0, 0.05]** | 23.15 | 356 | 0.01 |
| **(0.05, 67.718]** | 31.00 | 1237 | 27.82 |
| **(67.718, 109.81]** | 28.40 | 1240 | 93.50 |
| **(109.81, 120.93]** | 18.71 | 1240 | 115.24 |
| **(120.93, 130.55]** | 15.24 | 1238 | 125.88 |
| **(130.55, 140.801]** | 13.85 | 1236 | 135.51 |
| **(140.801, 154.504]** | 13.22 | 1238 | 147.51 |
| **(154.504, 172.888]** | 17.59 | 1238 | 163.25 |
| **(172.888, 519.29]** | 34.74 | 1239 | 203.30 |

</details>

<details>
<summary><b> 45-Day Rolling Window</b></summary>
<br>

| Price Bin (€/MWh) | MAE (€/MWh) | Sample Count | Avg Actual Price |
| :--- | :--- | :--- | :--- |
| **(-50.001, 0.0]** | 11.72 | 2122 | -1.46 |
| **(0.0, 0.05]** | 23.44 | 356 | 0.01 |
| **(0.05, 67.718]** | 31.52 | 1237 | 27.82 |
| **(67.718, 109.81]** | 28.68 | 1240 | 93.50 |
| **(109.81, 120.93]** | 18.99 | 1240 | 115.24 |
| **(120.93, 130.55]** | 15.07 | 1238 | 125.88 |
| **(130.55, 140.801]** | 13.65 | 1236 | 135.51 |
| **(140.801, 154.504]** | 13.09 | 1238 | 147.51 |
| **(154.504, 172.888]** | 17.82 | 1238 | 163.25 |
| **(172.888, 519.29]** | 36.83 | 1239 | 203.30 |

</details>

### Visualizing the Forecast (90-Day Rolling Window)


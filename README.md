
Device Performance Degradation Prediction
Project Overview: This project predicts the performance degradation of laptops over time using Support Vector Regression (SVR). The model uses multiple factors such as usage hours, temperature, load, voltage fluctuations, humidity, maintenance intervals, and fan speed to estimate the current performance on a scale of 0 to 100.
Features Explanation:
Feature	Description	Range	Effect on Performance
hours_used	Total cumulative hours the laptop has been used	0–1000+	Higher hours_used → lower performance
temperature	Current operating CPU/GPU temperature (°C)	30–80	Higher temperature → can reduce performance due to thermal throttling
load	Current CPU/GPU load (0 to 1)	0–1	Higher load → temporary performance drop
voltage_fluctuation	Variation in voltage supply (V)	±5	Higher fluctuations → can negatively affect performance
humidity	Environmental humidity (%)	20–80	Extreme humidity → may slightly reduce performance
maintenance_interval	Hours since last maintenance	0–200	Longer interval → higher risk of degraded performance
fan_speed	Cooling fan speed (RPM)	1000–3000	Lower fan_speed under high load → can lead to overheating and reduced performance
ML Workflow: 1. Load the dataset from CSV. 2. Separate features (X) and target (y). 3. Apply feature scaling using StandardScaler to normalize input and target. 4. Split data into training and testing sets. 5. Train SVR model with RBF kernel for non-linear regression. 6. Predict performance using scaled input, then inverse transform to original scale.
Manual Input & Prediction: - User inputs values for each feature (hours_used, temperature, load, voltage_fluctuation, humidity, maintenance_interval, fan_speed). - Input is scaled and fed into the trained SVR model. - Model outputs predicted performance score (0–100).
Sample Prediction: Example input: - hours_used: 500 - temperature: 42 - load: 0.8 - voltage_fluctuation: 1.5 - humidity: 50 - maintenance_interval: 100 - fan_speed: 2500
Predicted Laptop Performance: 72.35 / 100
How to Run: 1. Install required libraries: pandas, numpy, scikit-learn. 2. Place laptop_performance_dataset.csv in the project folder. 3. Run the Python script laptop_svr_predict.py in terminal. 4. Enter the requested feature values manually. 5. View predicted performance output.
Project Folder Structure:
device-performance-prediction/
│
├── laptop_performance_dataset.csv
├── laptop_svr_predict.py
├── README.md
└── docs/
    └── Device_Performance_Degradation_Prediction.docx
Output Interpretation: - Predicted performance score closer to 100 → Laptop is in good condition. - Score decreasing over time or with higher usage/temperature → Indicates degradation.
Future Improvements: - Include long-term average temperature as separate feature. - Collect real-world telemetry data for improved model accuracy. - Add more devices types (PC, mobile) and create device-specific models. - Use time-series models for continuous monitoring.

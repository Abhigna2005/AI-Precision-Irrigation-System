# AI-Driven Precision Irrigation System

An offline AI + IoT-based precision irrigation system that predicts whether irrigation is required using crop and environmental parameters, designed for smallholder farms in semi-arid regions of Karnataka.

## Features

- Predicts irrigation requirements using Machine Learning
- Uses soil moisture, temperature, humidity, rainfall, crop, and growth stage
- Arduino-based sensor integration
- SMS alerts using SIM800L
- Designed for Ragi, Groundnut, and Red Gram

## Machine Learning

Multiple classification models were evaluated:

| Model | Accuracy |
|---|---:|
| **Random Forest** | **91.48%** |
| Decision Tree | 87.90% |
| Naive Bayes | 76.83% |
| Logistic Regression | 76.70% |
| KNN | 72.07% |

Random Forest achieved the highest accuracy after hyperparameter tuning using GridSearchCV.

## Hardware

- Arduino UNO
- Soil Moisture Sensor
- DHT22
- Rain Sensor
- SIM800L GSM Module
- RTC DS1307
- I2C LCD
- Li-ion Battery

## Dataset

~5,000 samples containing:

`Crop | DAP | Growth Stage | Temperature | Humidity | Soil Moisture | Rainfall`

**Target:** `irrigation_needed`

## Technologies

**Python · Pandas · NumPy · Scikit-learn · Jupyter Notebook · Arduino C/C++**

## Repository

- `ml_training.ipynb` — ML training and evaluation
- `dataset_used.csv` — Dataset
- `crops_conditions.xlsx` — Crop condition data
- `arduino_code.ino` — Arduino implementation
- `connections.pdf` — Circuit connections
- `docs/` — Project documentation

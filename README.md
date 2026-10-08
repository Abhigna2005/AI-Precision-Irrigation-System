# AI-Driven Precision Irrigation System

An offline AI-driven precision irrigation system designed to help smallholder farmers make irrigation decisions using soil, weather, crop, and environmental parameters.

The system combines **machine learning with low-cost IoT hardware** to predict whether irrigation is required and provide a practical irrigation decision without relying on continuous internet connectivity.

## Features

-  Predicts whether irrigation is required using machine learning
-  Uses soil moisture, temperature, humidity, rainfall, crop, and growth-stage information
-  Compares multiple classification algorithms
-  Designed for offline operation with SMS-based alerts
-  Integrates Arduino-based sensing hardware
-  Designed for crops such as Ragi, Groundnut, and Red Gram
-  Uses a dataset containing approximately 5,000 samples
-  Suitable for resource-constrained smallholder farming environments

## System Overview

The system collects environmental and crop-related parameters and uses a trained machine learning model to determine whether irrigation is required.

```text
Sensors / Crop Data
        │
        ▼
┌─────────────────────┐
│ Data Preprocessing   │
└──────────┬──────────┘
           │
           ▼
┌─────────────────────┐
│ ML Classification    │
│ Model                │
└──────────┬──────────┘
           │
           ▼
   Irrigation Required?
        │       │
       Yes      No
        │       │
        ▼       ▼
   Alert /     No
 Irrigation   Irrigation
```

## Machine Learning

The project evaluates multiple classification algorithms for irrigation prediction:

| Model | Accuracy |
|---|---:|
| Random Forest | **91.48%** |
| Decision Tree | 87.90% |
| K-Nearest Neighbors | 72.07% |
| Naive Bayes | 76.83% |
| Logistic Regression | 76.70% |

Random Forest achieved the best performance after hyperparameter tuning using GridSearchCV, with an accuracy of **91.48%**.

## Dataset

The dataset contains approximately **5,000 records** with environmental and crop-related parameters.

### Input Features

- Crop
- Days After Planting (DAP)
- Growth Stage
- Temperature
- Humidity
- Soil Moisture
- Rainfall

### Target

```text
irrigation_needed
```

The target represents whether irrigation is required (`Yes` / `No`).

## Hardware

The prototype uses low-cost embedded hardware for collecting field parameters and communicating irrigation decisions.

### Components

- Arduino UNO
- Soil Moisture Sensor
- DHT22 Temperature & Humidity Sensor
- Rain Sensor
- SIM800L GSM Module
- RTC DS1307
- I2C LCD
- Li-ion Battery

### Hardware Workflow

```text
Soil Moisture ─┐
Temperature ───┤
Humidity ──────┤
Rainfall ──────┤
Crop / Stage ──┘
       │
       ▼
   Arduino UNO
       │
       ▼
 ML Irrigation Prediction
       │
       ├── Irrigation Required
       │          │
       │          ▼
       │      SMS Alert
       │
       └── No Irrigation
```

## Crops and Target Region

The system is designed with smallholder farming conditions in semi-arid regions of Karnataka in mind.

### Target Crops

- Ragi
- Groundnut
- Red Gram

### Target Regions

- Raichur
- Chitradurga
- Ballari
- Tumkur
- Koppal

## Repository Structure

```text
AI-Driven-Precision-Irrigation/
│
├── README.md
├── ml_training.ipynb
├── dataset_used.csv
├── crops_conditions.xlsx
├── arduino_code.ino
├── connections.pdf
│
└── docs/
    ├── write_up.pdf
    └── sources.docx
```

## Files

### `ml_training.ipynb`

Jupyter Notebook containing:

- Data preprocessing
- Exploratory analysis
- Model training
- Model comparison
- Hyperparameter tuning
- Accuracy evaluation

### `dataset_used.csv`

Dataset used for training and evaluating the irrigation prediction models.

### `crops_conditions.xlsx`

Supporting crop and environmental condition information used during the project.

### `arduino_code.ino`

Arduino implementation for interfacing with the sensors and hardware components.

### `connections.pdf`

Hardware wiring and circuit connection reference.

### `docs/write_up.pdf`

Detailed project documentation.

### `docs/sources.docx`

References and sources used during the project.

## Technologies Used

### Machine Learning

- Python
- Pandas
- NumPy
- Scikit-learn
- Jupyter Notebook
- GridSearchCV

### Embedded Systems

- Arduino UNO
- C/C++
- DHT22
- Soil Moisture Sensor
- Rain Sensor
- SIM800L
- RTC DS1307
- I2C LCD

## How to Run the ML Notebook

### 1. Clone the repository

```bash
git clone https://github.com/<your-username>/AI-Driven-Precision-Irrigation.git
cd AI-Driven-Precision-Irrigation
```

### 2. Install dependencies

```bash
pip install pandas numpy scikit-learn matplotlib seaborn openpyxl jupyter
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
ml_training.ipynb
```

and run the cells sequentially.

## Future Improvements

- Deploy the trained model directly on an edge device
- Add real-time sensor data ingestion
- Improve irrigation recommendations using weather forecasts
- Add multilingual SMS notifications
- Develop a mobile/web dashboard for farmers
- Expand the dataset across additional crops and regions
- Integrate automated irrigation control

## Project Objective

The goal of this project is to combine **machine learning, IoT, and low-cost hardware** to support data-driven irrigation decisions and reduce unnecessary water usage in smallholder farming environments.

## License

This project is intended for academic and educational purposes.

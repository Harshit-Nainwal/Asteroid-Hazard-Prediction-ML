# Asteroid Hazard Detection and Impact Risk Assessment using Machine Learning

## Overview

Near-Earth Objects (NEOs) such as asteroids pose potential risks to Earth if their orbits intersect with Earth's trajectory. Early detection and classification of **Potentially Hazardous Asteroids (PHAs)** is therefore critical for planetary defense.

This project presents a **hybrid AI + physics-based framework** for asteroid hazard prediction and impact risk assessment using machine learning and astrophysical modeling.

The system analyzes asteroid orbital and physical parameters from NASA's Small Body Database and predicts whether an asteroid is hazardous. It further estimates impact energy and evaluates environmental and societal risk.

---

## Research Contributions

This project introduces a **multi-stage asteroid risk assessment framework**:

1. Machine learning classification of hazardous asteroids
2. Explainable AI analysis of asteroid features
3. Physics-based impact energy modeling
4. Environmental hazard simulation
5. Societal risk scoring

This creates a more comprehensive approach compared to traditional asteroid classification systems.

---

## Dataset

The dataset is derived from the **NASA Small Body Database (SBDB)** and contains orbital and physical properties of Near-Earth Objects.

Key features used in the model:

| Feature                | Description                         |
| ---------------------- | ----------------------------------- |
| Absolute Magnitude (H) | Brightness of asteroid              |
| Diameter               | Estimated asteroid size             |
| Albedo                 | Surface reflectivity                |
| Eccentricity           | Orbit shape                         |
| Semi-major Axis        | Orbital size                        |
| Inclination            | Orbital tilt                        |
| Perihelion             | Closest distance to sun             |
| Aphelion               | Farthest distance from sun          |
| Earth MOID             | Minimum orbit intersection distance |

Target variable:

* **PHA (Potentially Hazardous Asteroid)**

---

## Methodology

### Data Preprocessing

The dataset undergoes several preprocessing steps:

* Column normalization
* Feature selection
* Numeric conversion
* Missing value handling
* Hazard label encoding

Missing asteroid diameters are estimated using the astronomical formula:

D = (1329 / sqrt(albedo)) × 10^(-H/5)

---

### Exploratory Data Analysis

EDA was performed to understand feature relationships.

Visualizations include:

* Correlation heatmap
* Hazard class distribution
* Feature importance analysis

---

### Class Imbalance Handling

Hazardous asteroids are rare events.

To handle class imbalance, **SMOTE (Synthetic Minority Oversampling Technique)** is applied to balance the dataset.

---

## Machine Learning Models

Four models were benchmarked using **5-fold Stratified Cross Validation**.

| Model               | Purpose                  |
| ------------------- | ------------------------ |
| Logistic Regression | Baseline linear model    |
| Random Forest       | Ensemble tree model      |
| XGBoost             | Gradient boosting model  |
| Neural Network      | Deep learning classifier |

Evaluation metrics:

* Accuracy
* F1 Score
* ROC-AUC
* Precision
* Recall

Random Forest achieved the best overall performance and was selected as the final model.

---

## Explainable AI (SHAP)

To improve interpretability, **SHAP (SHapley Additive Explanations)** was used to analyze feature contributions.

SHAP analysis provides:

* Global feature importance
* Model decision explanations
* Individual asteroid risk explanation

---

## Physics-Based Impact Modeling

Beyond classification, the system estimates asteroid impact consequences.

Impact energy is calculated using kinetic energy physics:

Energy = 0.5 × Mass × Velocity²

The model estimates:

* Blast radius
* Thermal damage radius
* Climate temperature drop
* Tsunami height (for ocean impacts)

---

## Societal Risk Scoring

A **multi-factor societal risk model** was developed to evaluate real-world impact.

The risk score incorporates:

* Hazard probability
* Impact energy
* Blast radius
* Climate effects
* Population density
* Economic exposure

The final risk score is normalized to a **0–100 scale**.

---

## Research Validation

Model validation includes:

* Confusion Matrix
* ROC Curve
* Calibration Curve
* Cross-validation benchmarking

These techniques ensure reliable model performance.

---

## Technologies Used

Programming Language:

* Python

Machine Learning:

* Scikit-Learn
* XGBoost
* TensorFlow / Keras

Data Analysis:

* Pandas
* NumPy

Visualization:

* Matplotlib
* Seaborn

Explainable AI:

* SHAP

Model Persistence:

* Joblib

---

## Project Structure

```
Asteroid-Hazard-Detection
│
├── data
│   └── sbdb_query_results.csv
│
├── notebooks
│   └── Asteroid_Detection.ipynb
│
├── figures
│   └── ROC_curves.png(example)
│
├── requirements.txt
│
└── README.md
```

---

## Applications

This framework can contribute to:

* Planetary defense research
* Space situational awareness
* Asteroid monitoring systems
* Scientific data mining in astrophysics
* AI-assisted space risk analysis

---

## Future Work

Potential extensions include:

* Real-time NASA NEO API integration
* Asteroid trajectory prediction using deep learning
* Reinforcement learning for asteroid deflection strategies
* Web dashboard for asteroid risk visualization

---

## Author

Harshit Nainwal
B.Tech Computer Science and Engineering (Regional)

---

## License

This project is intended for educational and research purposes.


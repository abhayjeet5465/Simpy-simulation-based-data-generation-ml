# Data Generation Using Modelling and Simulation for Machine Learning (SimPy)
By:Abhayjeet(102303761)
## Abstract
In many real-world scenarios, collecting large-scale labeled data is costly or impractical. Modelling and simulation provide an effective alternative by enabling controlled and repeatable data generation. This project uses **SimPy**, a Python-based discrete-event simulation library, to generate synthetic data from a single-server queue system. The generated dataset is then used to train and compare multiple machine learning models, and the best-performing model is identified using standard evaluation metrics.

---

## Overview
The project follows the complete pipeline required for simulation-driven machine learning:
- System modelling using discrete-event simulation
- Synthetic data generation through repeated simulations
- Supervised machine learning on generated data
- Model comparison and evaluation

---

## Simulation Tool
- **Library:** SimPy
- **Type:** Discrete-event simulation
- **Language:** Python

SimPy was chosen due to its simplicity, flexibility, and suitability for modeling queue-based service systems.

---

## System Description
The simulated system represents a **single-server service system (M/M/1 queue)**:
- Customers arrive randomly
- One server provides service
- Customers wait in a queue if the server is busy
- Service times are stochastic

---

## Simulation Parameters

| Parameter | Description | Range |
|---------|-------------|-------|
| Arrival Rate (λ) | Customer arrival rate | 0.1 – 5.0 |
| Service Rate (μ) | Server service rate | 0.5 – 10.0 |
| Simulation Time | Duration per run | 200 – 800 |
| Server Capacity | Number of servers | 1 |

---

## Data Generation
- Random parameter values are sampled within defined bounds
- Each parameter set is passed to the SimPy simulation
- Average waiting time is recorded per simulation
- **1000 independent simulations** are executed
- Results are stored as a structured dataset using Pandas

---

## Machine Learning Models
The generated dataset is used to predict **average waiting time** using the following regression models:
- Linear Regression
- Ridge Regression
- Lasso Regression
- Support Vector Regression (SVR)
- Random Forest Regressor
- Gradient Boosting Regressor
  
---

## Evaluation Metrics
- Root Mean Square Error (RMSE)
- Coefficient of Determination (R² Score)

---

## Results

| Model | RMSE | R² Score |
|------|------|----------|
| Linear Regression | 42.05 | 0.414 |
| Ridge Regression | 42.05 | 0.414 |
| Lasso Regression | 42.10 | 0.413 |
| SVR | 59.33 | -0.166 |
| Random Forest Regressor | **11.62** | **0.955** |
| Gradient Boosting Regressor | 12.09 | 0.952 |

**Best Performing Model:** Random Forest Regressor

Ensemble-based models significantly outperform linear models, as they are better suited to capture the non-linear behavior of queue-based systems.

---

---

## Conclusion
This project demonstrates that modelling and simulation can be effectively used to generate high-quality datasets for machine learning. SimPy enables controlled experimentation and realistic system behavior modelling. The results show that ensemble-based machine learning models, particularly Random Forest, can accurately learn from simulation-generated data, making this approach suitable when real-world data is limited.

---

## Tools and Technologies
- Python
- SimPy
- NumPy
- Pandas
- Scikit-learn
- Google Colab

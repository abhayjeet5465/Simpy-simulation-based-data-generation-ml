# Data Generation Using Modelling and Simulation for Machine Learning (SimPy)
by:Abhayjeet(102303761)

## Abstract
This project demonstrates the use of modelling and simulation for synthetic data generation using the SimPy discrete-event simulation framework. A queue-based service system is simulated to generate structured data under varying system parameters. The generated dataset is subsequently used to train and evaluate multiple machine learning models, and their performance is compared using standard regression metrics.

---

## 1. Simulation Tool Selection
For this assignment, **SimPy**, a Python-based discrete-event simulation library, was selected from the list of computer simulation software. SimPy is widely used for modeling real-world systems involving queues, limited resources, and time-dependent processes such as servers, manufacturing systems, and service centers.

**Justification for Selection:**
- Fully Python-based and compatible with Google Colab
- Supports discrete-event simulation
- Enables controlled parameter variation
- Suitable for large-scale synthetic data generation
- Easy integration with machine learning libraries

---

## 2. Installation and Exploration
The simulation environment was implemented using Google Colab. SimPy was installed using the Python package manager, and its core components such as Environment, Process, Resource, and Timeout were explored through a simple single-server queue simulation.

---

## 3. System Description and Parameters
The simulated system represents a **single-server service system** (M/M/1 queue), where entities arrive randomly, wait in a queue if the server is busy, and receive service when the resource becomes available.

### Input Parameters and Bounds

| Parameter | Description | Lower Bound | Upper Bound |
|--------|-------------|------------|------------|
| Arrival Rate (λ) | Mean arrival rate of customers | 0.1 | 5.0 |
| Service Rate (μ) | Mean service rate of server | 0.5 | 10.0 |
| Simulation Time | Total duration of simulation | 200 | 800 |
| Server Capacity | Number of servers | 1 | 1 |

---

## 4. Data Generation Methodology
A random set of parameters was generated within the specified bounds for each simulation run. These parameters were passed to the SimPy simulation model. During each run, key performance metrics such as average waiting time, average service time, and server utilization were recorded.

This process was repeated to ensure variability in system behavior and to generate a diverse dataset suitable for machine learning.

---

## 5. Simulation Runs
A total of **1000 independent simulations** were executed. Each simulation produced a single data record containing the input parameters and corresponding system performance metrics. All simulation outputs were aggregated into a structured dataset using Pandas.

---

## 6. Machine Learning Models
The generated dataset was used to train and evaluate multiple regression-based machine learning models to predict the average waiting time of the system.

### Models Evaluated
- Linear Regression
- Ridge Regression
- Lasso Regression
- Support Vector Regression (SVR)
- Random Forest Regressor
- Gradient Boosting Regressor
- XGBoost Regressor

---

## 7. Evaluation Metrics
The models were evaluated using the following performance metrics:
- Root Mean Square Error (RMSE)
- Mean Absolute Error (MAE)
- Coefficient of Determination (R² Score)

---

## 8. Results and Comparison
A comparative analysis was conducted across all models. Ensemble-based models demonstrated superior performance due to their ability to capture non-linear relationships inherent in simulation-generated data.

| Model | RMSE | MAE | R² Score |
|-----|-----|-----|---------|
| Linear Regression | Higher | Higher | Lower |
| Random Forest | Lower | Lower | Higher |
| Gradient Boosting | Lowest | Lowest | Highest |

**Best Performing Model:** Random Forest Regressor

---

## 9. Result Visualization
Graphical analysis was performed using scatter plots comparing actual versus predicted waiting times, demonstrating strong predictive performance for ensemble models.

---

## 10. Repository Structure
simulation-ml-simpy/
│
├── simpy_simulation.ipynb
├── data/
│ └── simulation_data.csv
├── README.md
└── requirements.txt

---

## 11. Conclusion
This project validates the effectiveness of modelling and simulation as a reliable approach for generating machine learning datasets. SimPy enables realistic system modeling, controlled experimentation, and scalable data generation. The results demonstrate that machine learning models trained on simulation-generated data can achieve high predictive accuracy, making this approach suitable for scenarios where real-world data is limited or unavailable.

---

## 12. Tools and Technologies
- Python
- SimPy
- NumPy
- Pandas
- Scikit-learn
- Google Colab

---

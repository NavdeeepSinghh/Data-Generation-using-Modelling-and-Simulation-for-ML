# 🚀 Data Generation using Modelling and Simulation for Machine Learning
### (PyBullet-Based Physics Simulation)

---

## 📌 Assignment Overview

This project demonstrates synthetic data generation using modelling and simulation, followed by machine learning model evaluation.

A physics-based simulator (**PyBullet**) is used to generate structured data under controlled physical conditions. The generated dataset is then used to train and compare multiple machine learning regression models.

The complete workflow is implemented using **Google Colab**, and results are hosted on GitHub.

---

## 🛠 Simulation Tool Used

### 🔹 PyBullet – Physics Simulation Engine

PyBullet is an open-source physics engine widely used for:

- Rigid body dynamics  
- Robotics  
- Reinforcement learning research  

It enables accurate modelling of physical interactions such as:

- Gravity  
- Friction  
- Collision  
- Energy dissipation  

### ✅ Why PyBullet?

- Fully Python-based  
- Compatible with Google Colab  
- Produces continuous numerical outputs  
- Suitable for machine learning dataset generation  

---

## 🧪 Simulation Description

### Scenario

A rigid cube is dropped from a specified height onto a flat surface under varying physical conditions.

The simulation captures how different physical parameters influence **energy loss during impact and motion**.

---

## 🔧 Simulation Parameters & Bounds

| Parameter     | Description                        | Lower Bound | Upper Bound |
|--------------|------------------------------------|------------|------------|
| mass         | Mass of cube (kg)                  | 0.5        | 5.0        |
| friction     | Surface friction coefficient       | 0.1        | 1.0        |
| restitution  | Coefficient of restitution         | 0.0        | 0.9        |
| height       | Initial drop height (m)            | 0.5        | 5.0        |
| gravity      | Gravitational acceleration (m/s²)  | 5          | 15         |

---

## 🎯 Output Variable (Target)

### Energy Loss (Joules)

Energy loss is computed as:

Initial Potential Energy − Final Resting Potential Energy

This serves as the regression target variable.

---

## 🔁 Data Generation Methodology

1. Randomly generate simulation parameters within defined bounds  
2. Run PyBullet simulation in **DIRECT (headless) mode**  
3. Compute energy loss for each simulation  
4. Store inputs and outputs in a structured dataset  
5. Repeat the process for **1000 simulations**  

---

## 📂 Generated Dataset

📄 **CSV File:**  
`pybullet_simulation_data.csv`

### Dataset Columns

| Column        | Description |
|--------------|------------|
| mass         | Cube mass |
| friction     | Friction coefficient |
| restitution  | Restitution coefficient |
| height       | Drop height |
| gravity      | Gravitational acceleration |
| energy_loss  | Target variable |

---

## 🤖 Machine Learning Models Used

The problem is formulated as a **regression task**.

The following models were trained and evaluated:

- Linear Regression  
- Ridge Regression  
- Lasso Regression  
- Decision Tree Regressor  
- Random Forest Regressor  
- Gradient Boosting Regressor  
- Support Vector Regressor (SVR)  

---

## 📊 Evaluation Metrics

Each model is evaluated using:

- MAE (Mean Absolute Error)  
- RMSE (Root Mean Squared Error)  
- R² Score  

---

## 📈 Results & Visualizations

### 🔹 Model Comparison (RMSE)

This graph compares the RMSE values of different machine learning models trained on the simulation-generated dataset.

Lower RMSE indicates better predictive performance.

<p align="center">
  <img src="Graphs/Model_Comparison(RMSE).png" width="650"><br>
  <em>Figure 1: RMSE comparison across regression models</em>
</p>

---

### 🔹 Best Model: Actual vs Predicted

The scatter plot below shows the relationship between actual and predicted energy loss values for the best-performing model (**Random Forest Regressor**).

The closer the points lie to the diagonal line, the better the model’s prediction accuracy.

<p align="center">
  <img src="Graphs/Best_Model.png" width="650"><br>
  <em>Figure 2: Actual vs Predicted Energy Loss</em>
</p>

---

### 🔹 Feature Importance (Best Model)

This plot highlights the relative importance of each input parameter in predicting energy loss.

It provides interpretability by showing which physical parameters most influence the outcome.

<p align="center">
  <img src="Graphs/Best_Feature.png" width="650"><br>
  <em>Figure 3: Feature Importance from Random Forest</em>
</p>

---

## 🏆 Best Performing Model

**Model:** Random Forest Regressor  
**Reason:** Lowest RMSE and Highest R² Score  

### 🔍 Insight

Non-linear ensemble models perform better for physics-based simulation data due to their ability to capture complex parameter interactions.

---

## 📓 Notebook

The complete implementation includes:

- Simulation code  
- Data generation  
- Machine learning training & evaluation  
- Graph generation  

📄 `Data_Generation.ipynb`

---

## 📁 Repository Structure


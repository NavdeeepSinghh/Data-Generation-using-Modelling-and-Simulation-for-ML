# 🚀 Data Generation using Modelling and Simulation for Machine Learning
### (PyBullet-Based Physics Simulation)

---

## 📌 Project Overview

This project demonstrates synthetic data generation using physics-based modelling and simulation, followed by machine learning model training and evaluation.

A PyBullet-based physics simulator is used to generate structured numerical data under controlled physical conditions. The generated dataset is then used to train and compare multiple regression-based machine learning models.

The complete workflow — simulation, dataset generation, model training, and evaluation — is implemented using Google Colab, and results are hosted on GitHub.

---

## 🛠 Simulation Engine

### 🔹 PyBullet – Physics Simulation Engine

PyBullet is an open-source physics engine widely used for:

- Rigid body dynamics  
- Robotics research  
- Reinforcement learning  
- Simulation-based ML pipelines  

It accurately models:

- Gravity  
- Friction  
- Collision  
- Energy dissipation  

### ✅ Why PyBullet?

- Fully Python-based  
- Compatible with Google Colab  
- Produces continuous numerical outputs  
- Ideal for synthetic ML dataset generation  

---

## 🧪 Simulation Scenario

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

## 🎯 Target Variable

### Energy Loss (Joules)

Energy loss is computed as:

Initial Potential Energy − Final Resting Potential Energy

This serves as the regression target variable.

---

## 🔁 Data Generation Pipeline

1. Randomly sample simulation parameters within defined bounds  
2. Run PyBullet in DIRECT (headless) mode  
3. Compute energy loss  
4. Store inputs and outputs in a structured dataset  
5. Repeat the process for 1000 simulations  

---

## 📂 Generated Dataset

📄 `pybullet_simulation_data.csv`

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

The problem is formulated as a regression task.

Models trained and evaluated:

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

This graph compares the RMSE values of different regression models.  
Lower RMSE indicates better predictive performance.

<p align="center">
  <img src="Graphs/Model_Comparison(RMSE).png" width="650"><br>
  <em>Figure 1: RMSE comparison across regression models</em>
</p>

---

### 🔹 Best Model: Actual vs Predicted (Random Forest)

The scatter plot shows the relationship between actual and predicted energy loss values for the best-performing model.

Points closer to the diagonal line indicate higher prediction accuracy.

<p align="center">
  <img src="Graphs/Best_Model.png" width="650"><br>
  <em>Figure 2: Actual vs Predicted Energy Loss (Random Forest)</em>
</p>

---

### 🔹 Feature Importance (Random Forest)

This visualization highlights the relative importance of each input parameter in predicting energy loss.

It provides interpretability into which physical parameters most influence system behavior.

<p align="center">
  <img src="Graphs/Best_Feature.png" width="650"><br>
  <em>Figure 3: Feature Importance from Random Forest</em>
</p>

---

## 🏆 Best Performing Model

**Model:** Random Forest Regressor  
**Reason:** Lowest RMSE and Highest R² Score  

### 🔍 Key Insight

Ensemble-based non-linear models outperform linear models on physics-based simulation data because they can capture complex parameter interactions.

---

## 📓 Notebook

The complete implementation includes:

- PyBullet simulation code  
- Synthetic dataset generation  
- Machine learning model training  
- Model comparison  
- Visualization generation  

📄 `Data_Generation.ipynb`

---

## 📁 Repository Structure


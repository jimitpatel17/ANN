# Artificial Neural Network (ANN) for Power Plant Energy Prediction

## 📌 Project Overview

This project implements an **Artificial Neural Network (ANN)** using **PyTorch** to predict the electrical energy output (PE) of a Combined Cycle Power Plant based on environmental conditions.

The project covers the complete machine learning workflow, from data preprocessing to model training, evaluation, and prediction.

---

## 📂 Dataset

The dataset contains measurements collected from a Combined Cycle Power Plant.

### Input Features

| Feature | Description |
|----------|-------------|
| AT | Atmospheric Temperature |
| V | Exhaust Vacuum |
| AP | Atmospheric Pressure |
| RH | Relative Humidity |

### Target Variable

| Target | Description |
|---------|-------------|
| PE | Electrical Energy Output |

---

## 🛠 Technologies Used

- Python
- PyTorch
- Pandas
- NumPy
- Scikit-learn
- Matplotlib

---

## 📖 Project Workflow

### Step 1: Load the Dataset

- Import the dataset using Pandas.
- Inspect the data.
- Check for missing values.

### Step 2: Data Preprocessing

- Separate input features (X) and target variable (y).
- Split data into training and testing sets.
- Scale the features using `StandardScaler`.

### Step 3: Convert Data to Tensors

- Convert NumPy arrays into PyTorch tensors.
- Create `TensorDataset`.
- Create `DataLoader` for batch training.

### Step 4: Build the ANN Model

The neural network consists of:

- Input Layer
- Hidden Layer 1
- ReLU Activation
- Hidden Layer 2
- ReLU Activation
- Output Layer

Example architecture:

```
Input (4 Features)
        │
Linear
        │
ReLU
        │
Linear
        │
ReLU
        │
Linear
        │
Output (Predicted PE)
```

---

## Step 5: Train the Model

During training:

- Forward propagation
- Loss calculation (MSE Loss)
- Backpropagation
- Optimizer updates
- Repeat for multiple epochs

Optimizer used:

- Adam

Loss Function:

- Mean Squared Error (MSE)

---

## Step 6: Evaluate the Model

After training:

- Switch model to evaluation mode using:

```python
model.eval()
```

- Disable gradient calculation:

```python
with torch.no_grad():
```

- Predict energy output on test data.

---

## Step 7: Save the Model

Save trained weights:

```python
torch.save(model.state_dict(), "ann_model.pth")
```

---

## Step 8: Load the Saved Model

```python
model = ANN()
model.load_state_dict(torch.load("ann_model.pth"))
model.eval()
```

---

## Project Structure

```
ANN-Implementation/
│
├── ANN(implementation).ipynb
├── powerplant_data.csv
├── ann_model.pth
├── README.md
└── requirements.txt
```

---

## Installation

Clone the repository:

```bash
git clone https://github.com/yourusername/ANN-Implementation.git
```

Install dependencies:

```bash
pip install -r requirements.txt
```

---

## Required Libraries

```text
torch
numpy
pandas
matplotlib
scikit-learn
```

---

## Running the Project

Open the notebook:

```bash
jupyter notebook
```

Run each cell sequentially to:

1. Load data
2. Preprocess data
3. Train the ANN
4. Evaluate the model
5. Save the trained model

---

## Learning Outcomes

This project demonstrates how to:

- Build an ANN using PyTorch
- Perform regression using neural networks
- Convert data into tensors
- Use DataLoader for mini-batch training
- Train a neural network using backpropagation
- Save and load trained models
- Make predictions on unseen data

---

## Future Improvements

- Hyperparameter tuning
- Early stopping
- Dropout regularization
- Batch normalization
- Learning rate scheduling

---

## Author

**Jimit Kachchhi**

B.Tech Information Technology  
Machine Learning & Data Analytics
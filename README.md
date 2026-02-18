## Overview

This code demonstrates a **simple linear regression model implemented using PyTorch**.  
The goal is to predict **house prices** based on **house size (in square feet)** using a small sample dataset.  
The workflow covers data preparation, model definition, training, visualization, and prediction.

---

## Libraries Used

- **torch** – Core PyTorch library for tensor operations and model training  
- **torch.nn** – Provides neural network layers and loss functions  
- **numpy** – Used for numerical data handling  
- **matplotlib.pyplot** – Used to visualize training loss  

---

## Dataset Preparation

- A small dataset is created manually using NumPy.
- Each row contains:
  - Column 1: House size (sq ft)
  - Column 2: House price
- The dataset is split into:
  - `X` → input feature (house size)
  - `y` → target output (price)

---

## Data Preprocessing

- Both input and output values are **standardized**.
- Mean and standard deviation are calculated separately for `X` and `y`.
- Standardization helps improve training stability and convergence.
- The processed NumPy arrays are converted into **PyTorch tensors**.

---

## Model Definition

- A custom class `LinearRegressionModel` is defined using `nn.Module`.
- The model contains:
  - One linear layer (`nn.Linear`) with:
    - 1 input feature
    - 1 output value
- The `forward` method defines how input data flows through the model.

---

## Loss Function and Optimizer

- **Mean Squared Error (MSE)** is used as the loss function.
- **Stochastic Gradient Descent (SGD)** is used as the optimizer.
- A small learning rate is chosen to ensure stable training.

---

## Training Process

- The model is trained for **5000 epochs**.
- Each training loop includes:
  - Forward pass to generate predictions
  - Loss computation
  - Gradient reset
  - Backpropagation
  - Weight update
- Loss values are stored for later visualization.
- Training progress is printed every 100 epochs.

---

## Loss Visualization

- The loss values collected during training are plotted.
- The graph shows how the model error decreases over time.
- This helps verify that the model is learning properly.

---

## Making a Prediction

- A house size of **2500 sq ft** is provided as input.
- The input is standardized using the same statistics as training data.
- The trained model predicts a scaled price.
- The predicted value is converted back to the original price scale.
- The final predicted price is printed.

---

## Key Takeaways

- This code shows a complete **end-to-end linear regression workflow** in PyTorch.
- It includes:
  - Manual dataset handling
  - Data normalization
  - Model creation
  - Training loop
  - Performance visualization
  - Real-world prediction
- The structure follows standard PyTorch best practices for simple regression tasks.

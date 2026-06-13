# Profit Prediction with Linear Regression

*Predict restaurant franchise profitability based on city population using a custom-built batch gradient descent linear regression model.*

![Build](https://img.shields.io/badge/build-passing-brightgreen)
![License](https://img.shields.io/badge/license-MIT-blue)
![Python](https://img.shields.io/badge/python-3.11+-yellow)
![Jupyter](https://img.shields.io/badge/jupyter-%23F37626.svg?logo=jupyter&logoColor=white)

Profit Prediction with Linear Regression is a data-driven model designed to estimate franchise monthly profits based on city population sizes. Implementing fundamental machine learning concepts from the ground up, this project models the relationship between population density and potential profits.

Rather than relying on high-level machine learning frameworks, this implementation defines the mathematical formulations for the cost function and batch gradient descent algorithm from scratch using NumPy. It helps business executives, franchise developers, and analysts identify high-potential target expansion cities by providing a clean, transparent, and lightweight predictive tool.

---

## 📑 Table of Contents

- [Profit Prediction with Linear Regression](#profit-prediction-with-linear-regression)
  - [Table of Contents](#-table-of-contents)
  - [Features](#features)
  - [Technology Stack](#technology-stack)
  - [Demo and Preview](#demo-and-preview)
  - [Installation](#installation)
  - [Usage](#usage)
  - [Configuration](#configuration)
  - [Testing](#testing)
  - [License](#license)
  - [FAQs](#faqs)
  - [Contact](#contact)

---

## 🚀 Features

* **Custom Cost Function:** Evaluates prediction accuracy using a manually implemented mean squared error cost algorithm ($J(w, b)$).
* **Batch Gradient Descent:** Updates fitting parameters ($w$ and $b$) simultaneously using gradient computations to minimize loss.
* **Single-Variable Linear Regression:** Maps city populations directly to franchise monthly profits.
* **Interactive Visualization:** Generates detailed scatter plots of the dataset alongside the best-fit regression line using Matplotlib.
* **Forecasting Tool:** Predicts expected monthly franchise profits for any user-defined city population size.
* **Built-in Verification Suite:** Includes a standalone test suite to verify math formulas and prevent regressions.

---

## 🛠 Technology Stack

* **Language:** Python 3.11+
* **Data Processing:** NumPy
* **Visualization:** Matplotlib
* **Environment:** Jupyter Notebook
* **Testing:** Custom Unit Tests (`public_tests.py`)

---

## 📊 Demo and Preview

The regression model fits a linear boundary to the dataset to help locate highly profitable zones.

* **Linear Fit Plot:** A custom scatter plot displays 97 historical data points (city population vs. average profit) overlaid with a blue linear fit line ($f_{w,b}(x) = wx + b$) trained by batch gradient descent.
* **Profit Predictions:**
  * For a population of **35,000**, the model predicts a monthly franchise profit of **$4,519.77**.
  * For a population of **70,000**, the model predicts a monthly franchise profit of **$45,342.45**.

For a detailed walkthrough of the implementation process and results, you can read the article on [Medium](https://medium.com/@thejayshah2002/profit-prediction-with-linear-regression-model-c4c2fd68587a) or browse the code in the [GitHub Repository](https://github.com/js-92/Profit-Prediction-with-Linear-Regression.git).

---

## 💻 Installation

Follow these steps to set up and run the project locally:

### Prerequisites
Make sure you have Python 3.11+ and pip installed.

### Setup Instructions

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/js-92/Profit-Prediction-with-Linear-Regression.git
   cd profit-forecasting-model
   ```

2. **Create a Virtual Environment (Optional but recommended):**
   ```bash
   python3 -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```

3. **Install Dependencies:**
   ```bash
   pip install numpy matplotlib jupyter
   ```

---

## 📈 Usage

1. **Launch the Notebook Server:**
   ```bash
   jupyter notebook
   ```

2. **Open the Notebook:**
   Navigate to and open [profit-forecasting.ipynb](file:///Users/jayshah/Downloads/jayshah-92/profit-forecasting-model/profit-forecasting.ipynb).

3. **Run the Cells:**
   Execute the cells in sequence. The workflow will:
   * Load population and profit data from the dataset (`data/ex1data1.txt`).
   * Visualize the data in a scatter plot.
   * Run unit tests to verify the cost and gradient calculations.
   * Train the parameters $w$ and $b$ using batch gradient descent for 1,500 iterations at a learning rate of $\alpha = 0.01$.
   * Plot the regression line on top of the dataset.
   * Perform inference to predict profits for cities with 35,000 and 70,000 people.

---

## ⚙️ Configuration

Hyperparameters can be tuned inside the training cell of [profit-forecasting.ipynb](file:///Users/jayshah/Downloads/jayshah-92/profit-forecasting-model/profit-forecasting.ipynb):

* **Learning Rate (`alpha`):** Controls the step size at each gradient update. Default is set to `0.01`. Too large a value may cause divergence, while too small a value slows down convergence.
* **Iterations (`iterations`):** The number of gradient descent updates to perform. Default is set to `1500`.
* **Data Loader:** By default, `utils.py` uses `load_data()` to ingest `data/ex1data1.txt`. You can switch to `load_data_multi()` for multi-feature datasets.

---

## 🧪 Testing

This project uses a dedicated testing suite [public_tests.py](file:///Users/jayshah/Downloads/jayshah-92/profit-forecasting-model/public_tests.py) to check the correctness of key functions.

Run these test assertions directly in the notebook:
```python
from public_tests import *

# Verify the cost function implementation
compute_cost_test(compute_cost)

# Verify the gradient calculation implementation
compute_gradient_test(compute_gradient)
```

### Expected Output
When all calculations are correct, the terminal/notebook will output:
```text
Cost at initial w: 75.203
All tests passed!

Gradient at initial w, b (zeros): -65.3288497455567 -5.839135051546393
Using X with shape (4, 1)
All tests passed!
```

---

## 📄 License

This project is licensed under the MIT License. See the [LICENSE](file:///Users/jayshah/Downloads/jayshah-92/profit-forecasting-model/LICENSE) file for the full text.

---

## ❓ FAQs

### Why is my cost function returning `NaN` or increasing with every iteration?
This usually means your learning rate ($\alpha$) is too high. If the steps are too large, the optimizer overshoots the minimum and diverges. Try reducing `alpha` (e.g., to `0.001` or `0.0001`) and re-running.

### Can I run this with multiple features (e.g., advertising spend, land cost)?
The notebook is configured for single-variable linear regression. However, the helper file [utils.py](file:///Users/jayshah/Downloads/jayshah-92/profit-forecasting-model/utils.py) contains a `load_data_multi()` function to load multi-feature data files (such as `data/ex1data2.txt`), which can be used to extend the project into a Multiple Linear Regression model.

### Where can I find the raw dataset?
The raw data files are stored in the `data/` directory. The main dataset is `ex1data1.txt` which has population size as the first column and monthly profit as the second column.

---

## ✉️ Contact

* **Author:** Jay Shah
* **GitHub:** [jayshah-92](https://github.com/jayshah-92)
* **Medium Profile:** [@thejayshah2002](https://medium.com/@thejayshah2002)

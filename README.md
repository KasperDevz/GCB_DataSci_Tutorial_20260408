# Supply Chain Optimization Project (MILP Model)

This project demonstrates a complete workflow for supply chain data management, from synthetic data generation to production planning optimization using **Mixed-Integer Linear Programming (MILP)**.

## Project Structure
The project is divided into 3 main phases across 4 Jupyter Notebooks:

### 1. Data Generation
* **File:** `workshop1_data_generation.ipynb`
* **Purpose:** To create synthetic business data for testing the model.
* **How to use:** Run this notebook first to generate the raw environment.
* **Result:** You will get 4 initial CSV files:
    1. `01-inventory.csv`: Current stock of raw materials (RM).
    2. `02-recipe.csv`: Ingredients/Recipes for each product.
    3. `03-orders.csv`: Customer orders with manufacturing dates.
    4. `04-git.csv`: Goods in Transit (expected incoming RM deliveries).

### 2. Data Preparation
* **File:** `Workshop2_data_preparation_final.ipynb`
* **Purpose:** To clean the raw data and prepare it for optimization (Data Wrangling).
* **How to use:** Run this after Workshop 1. It handles date formatting and groups data into "Time Buckets".
* **Result:** You will get 3 processed CSV files:
    1. `05-recipe-summary.csv`: Summarized cost and usage per recipe.
    2. `06-orders-time-bucket.csv`: Orders assigned to specific time intervals (Buckets).
    3. `07-git-time-bucket.csv`: Incoming RM deliveries mapped to time intervals.

### 3. Optimization Modeling (MILP)
* **Files:** `Workshop3_MILP_Model.ipynb` and `Workshop3_2_MILP_Model.ipynb`
* **Purpose:** The core engine that decides which orders can be produced based on RM availability to maximize profit or success rate.
* **Differences:** * `Workshop3_MILP_Model`: The standard optimization model.
    * `Workshop3_2_MILP_Model`: An advanced version with improved priority logic for handling complex scenarios.
* **How to use:** Run these notebooks last to solve the production puzzle.
* **Result:**
    * `11-summary.csv`: A high-level report showing the overall **Success Rate (%)** and total production values.
    * `11-mo-shortage-details.csv`: A detailed report explaining exactly which raw materials are missing for the "Skipped" orders.

---

## Getting Started for Beginners

1.  **Environment Setup:** Make sure you have Python installed with the following libraries:
    ```bash
    pip install pandas numpy scipy
    ```
2.  **Order of Execution:** Follow the sequence: `Workshop 1` → `Workshop 2` → `Workshop 3`.
3.  **Concept of "Time Buckets":** Instead of checking inventory every single day, this project groups dates into 7-day windows (Buckets). This makes the optimization calculation faster and more realistic for real-world planning.

## Key Outcomes
By following these workshops, you will see how data science can transform a chaotic list of orders into a **feasible production plan** that ensures you only start jobs you have the materials for, reducing waste and delays.

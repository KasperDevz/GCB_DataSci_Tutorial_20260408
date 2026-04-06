# Supply Chain Optimization Project (MILP Model)

This project provides a step-by-step workflow for optimizing production plans based on raw material availability using Mixed-Integer Linear Programming (MILP).

## 📁 Project Workflow & File Outputs

### 1. Data Generation Phase
**File:** `workshop1_data_generation.ipynb`
**Description:** Generates initial synthetic data to simulate a factory environment.

| Output Filename | Description |
| :--- | :--- |
| `01-inventory.csv` | Current stock of raw materials in the warehouse. |
| `02-recipe.csv` | Bill of Materials (BOM) showing ingredients needed for each product. |
| `03-orders.csv` | Customer purchase orders with quantities and requested dates. |
| `04-git.csv` | Goods in Transit (Expected incoming raw material deliveries). |

---

### 2. Data Preparation Phase
**File:** `Workshop2_data_preparation_final.ipynb`
**Description:** Cleans raw data and transforms dates into "Time Buckets" (Weekly intervals).

| Output Filename | Description |
| :--- | :--- |
| `05-recipe-summary.csv` | Calculated production costs for each product recipe. |
| `06-orders-time-bucket.csv` | Orders mapped to 7-day time intervals. |
| `07-git-time-bucket.csv` | Material deliveries mapped to 7-day time intervals. |

---

### 3. Optimization Modeling Phase (Choice of 2 Models)

#### 🟢 Option A: Standard Model
**File:** `Workshop3_MILP_Model.ipynb`
**Focus:** Maximum Volume. It finds the highest number of orders that can be physically produced.

| Output Filename | Description |
| :--- | :--- |
| `07-orders-calculation.csv` | Final production plan (Is_Producible: True/False). |
| `11-summary.csv` | Report on Total Produced Qty and Success Rate. |
| `11-mo-shortage-details.csv` | List of missing materials for each "False" order. |

#### 🔵 Option B: Advanced Priority Model
**File:** `Workshop3_2_MILP_Model.ipynb`
**Focus:** Business Value. It prioritizes high-value or urgent orders when materials are limited.

| Output Filename | Description |
| :--- | :--- |
| `07-orders-priority-calc.csv` | Optimized plan based on business priority/value. |
| `11-summary.csv` | Summary report with optimized total value and counts. |
| `11-mo-shortage-details.csv` | Detailed shortage report with precise missing amounts. |

---

## 🚀 How to Run on Google Colab (Recommended)

Google Colab is the easiest way to run this project without installing anything on your computer.

### Step 1: Upload Files
1. Go to [Google Colab](https://colab.research.google.com/).
2. Click **File > Upload notebook** and upload the `.ipynb` files.
3. On the left sidebar, click the **Folder icon** 📁 and upload any required CSV files (if you are starting from a middle step).

### Step 2: Execute in Order
You must run the notebooks in this specific sequence because each step generates the files needed for the next:
1.  **Run `Workshop 1`**: To generate the 01-04 CSV files.
2.  **Run `Workshop 2`**: To process them into 05-07 CSV files.
3.  **Run `Workshop 3`**: To get your final optimization results.

### Step 3: Run Cells
* Click inside a code block and press `Shift + Enter` or click the **Play button** (▶️) on the left of the cell.
* If you see a green checkmark ✅, it means the step is complete and the output CSV has been created.

### Step 4: Download Results
* After running the final workshop, go to the **Folder icon** 📁 on the left again.
* You will see the new files (like `11-summary.csv`).
* Right-click the file and select **Download** to view it in Excel.

---

## 💡 Pro Tip
If you close your Colab tab, the temporary files might be deleted. It is recommended to run all steps in one session to ensure the data flows correctly from Workshop 1 to Workshop 3.

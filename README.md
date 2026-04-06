# Supply Chain Optimization Project (MILP Model)

This project provides a step-by-step workflow for optimizing production plans based on raw material availability.

## 📁 Project Workflow & File Outputs

### 1. Data Generation Phase
**File:** `workshop1_data_generation.ipynb`
**Description:** Generates initial synthetic data to simulate a factory environment.

| Output Filename | Description |
| :--- | :--- |
| `01-inventory.csv` | Current stock of raw materials in the warehouse. |
| `02-recipe.csv` | Bill of Materials (BOM) showing which ingredients are needed for each product. |
| `03-orders.csv` | Customer purchase orders with quantities and requested dates. |
| `04-git.csv` | Goods in Transit (Expected incoming raw material deliveries). |

---

### 2. Data Preparation Phase
**File:** `Workshop2_data_preparation_final.ipynb`
**Description:** Cleans the raw data and transforms dates into "Time Buckets" (Weekly intervals).

| Output Filename | Description |
| :--- | :--- |
| `05-recipe-summary.csv` | Calculated production costs for each product based on ingredients. |
| `06-orders-time-bucket.csv` | Orders reorganized into weekly periods for the optimizer. |
| `07-git-time-bucket.csv` | Material deliveries reorganized into weekly periods. |

---

### 3. Optimization Modeling Phase (Choice of 2 Models)

#### 🟢 Option A: Standard Model
**File:** `Workshop3_MILP_Model.ipynb`
**Description:** Uses MILP to find the maximum possible production volume.

| Output Filename | Description |
| :--- | :--- |
| `07-orders-calculation.csv` | The production plan (Marked as Producible: Yes/No). |
| `11-summary.csv` | Executive summary: Total orders produced vs. total cost. |
| `11-mo-shortage-details.csv` | List of missing materials for each failed order. |

#### 🔵 Option B: Advanced Priority Model
**File:** `Workshop3_2_MILP_Model.ipynb`
**Description:** An upgraded model that uses "Weighted Priority" to ensure high-value orders are produced first when materials are scarce.

| Output Filename | Description |
| :--- | :--- |
| `07-orders-priority-calc.csv` | Production plan optimized by business priority/value. |
| `11-summary.csv` | Summary report with success rates and total optimized value. |
| `11-mo-shortage-details.csv` | Detailed shortage report with precise amounts of missing ingredients. |

---

## 🚀 How to Run

1. **Install Dependencies:**
   ```bash
   pip install pandas numpy scipy

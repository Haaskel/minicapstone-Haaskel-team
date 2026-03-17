# 💊 Drug Inventory & Expiry Manager
**SPARK2026 Mini Capstone — Project #06**

A command-line pharmacy management tool built in Python. It loads drug stock data from a CSV file, flags expired or low-stock medications, generates restocking alerts, and produces inventory visualisations — all through an interactive menu-driven interface.

---

## 📋 What the Project Does

The Drug Inventory & Expiry Manager helps pharmacy staff maintain accurate stock control by:

- **Loading and cleaning** drug inventory data from a CSV file, handling missing values and invalid records automatically
- **Flagging expired drugs** and those expiring within 30 days, with days-to-expiry calculations
- **Identifying low-stock items** by comparing current quantity against each drug's reorder level
- **Generating restocking reports** that list every drug requiring replenishment
- **Searching the inventory** by drug ID, name, or therapeutic category
- **Visualising the inventory** through three chart types:
  - Bar chart of top drugs by stock level
  - Pie chart of drug distribution by category
  - Line chart of cumulative stock value by expiry date
- **Calculating total stock value** across all drugs in the inventory

The system is built around two OOP classes — `Drug` (single item logic) and `Inventory` (collection management) — and is navigated via a numbered main menu in the notebook's interactive output.

---

## 🚀 How to Run the Project

### 1. Prerequisites

Ensure you have **Python 3.8+** installed. Then install the required libraries:

```bash
pip install pandas matplotlib seaborn
```

> All other modules used (`datetime`, `csv`) are part of Python's standard library.

### 2. Prepare the Data File

Place the inventory CSV file in the **same directory** as the notebook. The file must be named:

```
06_drug_inventory.csv
```

The CSV should contain the following columns:

| Column | Description |
|---|---|
| `drug_id` | Unique drug identifier (e.g. `DRG001`) |
| `drug_name` | Name of the medication |
| `category` | Therapeutic category (e.g. Antibiotic, Analgesic) |
| `quantity_in_stock` | Current units available |
| `reorder_level` | Minimum stock threshold before restocking |
| `unit_price_usd` | Price per unit in USD |
| `expiry_date` | Expiry date in `YYYY-MM-DD` format |
| `form` | Dosage form (e.g. Tablet, Capsule, Syrup) |
| `supplier` | Supplier name |

### 3. Open the Notebook

Launch the notebook in **Jupyter Lab**, **VS Code**, or **Google Colab**:

```bash
jupyter lab drug_inventory_manager.ipynb
```

Or upload it directly to [Google Colab](https://colab.research.google.com/) along with the CSV file.

### 4. Run All Cells

Execute all cells from top to bottom in order:

- **Kernel → Restart & Run All** (Jupyter) 
- **Runtime → Run all** (Google Colab)

The final cell calls `run_pharmacy_manager()`, which launches the interactive menu.

### 5. Navigate the Menu

Once running, you will see:

```
====== PHARMACY INVENTORY MANAGER ======
1. Drug Inquiry (Search, Details)
2. Inventory Reports (Expiry, Low Stock)
3. Chart Generation (Visualizations)
4. Exit
========================================
Enter your choice:
```

Enter a number and follow the on-screen prompts to explore the inventory.

---

## 👥 Team

| Name | Task |
|---|---|
| *(Team Member 1)* | Built the `Drug` class — properties, expiry logic (`is_expired`, `is_expiring_soon`, `days_to_expiry`), stock value calculation, and status summary |
| *(Team Member 2)* | Built the `Inventory` class — collection management, `load_stock`, `get_drug_by_id`, `get_by_category`, and `summary_dataframe` |
| *(Team Member 3)* | Handled data loading and cleaning — `load_stock()` function, missing value imputation, type coercion, and summary statistics |
| *(Team Member 4)* | Built expiry and restock reporting — `check_expiry()` and `generate_restock_report()` functions |
| *(Team Member 5)* | Created visualisations — bar chart (top drugs by stock), pie chart (category distribution), and line chart (cumulative stock value by expiry date) |
| *(Team Member 6)* | Built the interactive menu system — `run_pharmacy_manager()`, `handle_drug_inquiry()`, `handle_inventory_reports()`, and `handle_chart_generation()` |

> **Note:** Replace the placeholder names above with each team member's full name before submitting.

---

## 📁 Project Structure

```
project-06/
├── drug_inventory_manager.ipynb   # Main notebook
├── 06_drug_inventory.csv          # Input data file
└── README.md                      # This file
```

---

## 📦 Dependencies

```
pandas
matplotlib
seaborn
```

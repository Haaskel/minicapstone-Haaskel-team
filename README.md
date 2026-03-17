# 💊 Drug Inventory & Expiry Manager
**SPARK2026 Mini Capstone — Project #06 | Team 6 · Nigeria-Abuja**

A Python-based pharmacy management tool that loads drug stock data from a CSV file, flags expired and low-stock medications, generates restocking and expiry reports, and produces inventory visualisations — all through an interactive terminal menu.

---

## 📋 What the Project Does

The Drug Inventory & Expiry Manager helps pharmacy staff maintain accurate, proactive stock control by:

- **Loading and cleaning** drug inventory data from a CSV file, dropping rows with missing values and enforcing correct data types
- **Analysing drug pricing** by identifying the most expensive and cheapest drugs, and computing total inventory value per supplier
- **Tracking stock levels** by identifying low-stock drugs (within 15 units of the reorder level) and those needing restocking soon (within 20 units of the reorder level)
- **Monitoring expiry dates** by flagging already-expired drugs and those expiring within a configurable window (default: 30–90 days)
- **Forecasting expiry losses** by calculating the total monetary value of stock at risk of expiring within 30, 60, or 90 days
- **Generating text reports** — a restock report and an expiry report — both printable to the console and saveable as `.txt` files
- **Visualising the inventory** through three chart types:
  - Bar chart of top N drugs by stock level
  - Pie chart of drug distribution by therapeutic category
  - Timeline chart of drug stock quantity by expiry date
- **Providing a 7-option terminal menu** for navigating all features interactively

The system is built around two OOP classes — `Drug` (price and supplier analysis) and `Inventory` (stock management, reporting, and expiry tracking) — alongside standalone wrapper functions and dedicated chart functions.

---

## 🚀 How to Run the Project

### 1. Prerequisites

Ensure you have **Python 3.8+** installed. Then install the required libraries:

```bash
pip install pandas matplotlib seaborn
```

> All other modules used (`datetime`) are part of Python's standard library.

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
| `form` | Dosage form (e.g. Tablet, Capsule, Injection, Sachet) |
| `supplier` | Supplier name |

### 3. Open the Notebook

Launch the notebook in **Jupyter Lab**, **VS Code**, or **Google Colab**:

```bash
jupyter lab team_6_abuja.ipynb
```

Or upload it directly to [Google Colab](https://colab.research.google.com/) along with the CSV file.

### 4. Run All Cells

Execute all cells from top to bottom in order:

- **Kernel → Restart & Run All** (Jupyter)
- **Runtime → Run all** (Google Colab)

This will import libraries, load and clean the data, define all classes and functions, and then launch the interactive menu via the final `main()` call.

### 5. Navigate the Menu

Once running, you will see:

```
Welcome to the Drug Inventory Management System!

--- Main Menu ---
1. Load Inventory Data
2. View Drug Summaries
3. View Inventory Summaries
4. Generate Restock Report
5. Generate Expiry Report
6. Generate Charts
7. Exit
```

Enter a number and follow the on-screen prompts. **Always start with option 1** to load the inventory before using any other feature.

---

## 👥 Team

| Name | Task |
|---|---|
| *(Team Member 1)* | Built the `Drug` class — `price_summary()`, `supplier_summary()`, `total_inventory_value()`, and `description()` methods |
| *(Team Member 2)* | Built the `Inventory` class — `get_low_stock()`, `get_re_stock()`, `stock_summary()`, `check_expiry()`, `near_expiry()`, and `expiry_loss_forecast()` methods |
| *(Team Member 3)* | Built `Inventory` report methods — `restock_report()` and `expiry_report()`, including file export to `.txt` |
| *(Team Member 4)* | Wrote standalone functions — `load_stock()` for data loading and cleaning, `generate_restock_report()`, and `generate_expiry_report()` |
| *(Team Member 5)* | Created visualisations — `plot_stock_levels()` (bar chart), `plot_drug_categories()` (pie chart), and `plot_stock_by_expiry_timeline()` (timeline chart) |
| *(Team Member 6)* | Built the terminal application — `main()` menu loop with all 7 options wired to the correct classes and functions |

> **Note:** Replace the placeholder names above with each team member's full name before submitting.

---

## 📁 Project Structure

```
project-06/
├── team_6_abuja.ipynb         # Main notebook
├── 06_drug_inventory.csv      # Input data file
├── restock_report.txt         # Generated restock report (after running option 4)
├── expiry_report.txt          # Generated expiry report (after running option 5)
└── README.md                  # This file
```

---

## 📦 Dependencies

```
pandas
matplotlib
seaborn
```

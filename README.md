# Retail Supplier Performance Analysis
A data analysis project to optimize supplier performance in retail, inspired by Musgrave. Built with Python, SQL, and Power BI.

## Project Overview
This project analyzes supplier performance and engagement for a retail scenario (simulating a supermarket like Musgrave), using the Online Retail dataset. The purpose is to evaluate key metrics such as delivery reliability, profitability, and return rates, providing actionable insights for business optimization.

## Data Source
- **Dataset**: `Online Retail.xlsx` (541,909 rows) with columns: `InvoiceNo`, `StockCode`, `Description`, `Quantity`, `InvoiceDate`, `UnitPrice`, `CustomerID`, and `Country`.
- **Location**: Stored in the `notebooks/` folder for initial exploration.
- **Source**: Downloaded from the UCI Machine Learning Repository[](https://archive.ics.uci.edu/dataset/352/online+retail).

## Data Exploration and Organization
- **Initial Assessment**:
  - Total rows: 541,909.
  - Identified issues: 1,454 missing `Description` values (0.27%), 135,080 missing `CustomerID` values (24.93%), 10,624 rows with negative `Quantity` (1.96%) indicating returns, 2 rows with negative `UnitPrice` (0.0004%) labeled "adjust bad debt", and 2,517 rows with `UnitPrice` = 0 (0.46%) often with non-zero `Quantity`.
- **Cleaning Decisions**:
  - Imputed missing `Description` with "Unknown" to retain rows for item-level analysis.
  - Imputed missing `CustomerID` with "Unknown" where `Quantity` and `UnitPrice` were available, preserving financial and volume metrics.
  - Added `IsReturn` flag for negative `Quantity` rows to analyze returns separately.
  - Added `IsBadDebt` flag for negative `UnitPrice` rows for financial impact analysis.
  - Added `IsZeroPrice` flag for `UnitPrice` = 0 with non-zero `Quantity` for volume analysis.
- **Outcome**: The dataset is now organized in `notebooks/01_Data_Exploration_and_Cleaning.ipynb`, ready for further analysis with cleaned and flagged data.

## Usage
1. Clone the repository: `git clone https://github.com/seu-usuario/Retail-Supplier-Performance-Analysis.git`
2. Navigate to `notebooks/` and open `01_Data_Exploration_and_Cleaning.ipynb` with Jupyter Notebook or VS Code.
3. Ensure `Online Retail.xlsx` is in the `notebooks/` folder.


## Contact
For questions, contact [https://www.linkedin.com/in/victor-garlet/].

*Last Updated: August 20, 2025*

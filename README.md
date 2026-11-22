# 6BUIS017W CWK1 – Market Analysis and Stock Segmentation Using RFM

Business intelligence analysis of S&P 500 shares using weekly return, weekly beta and adapted
Recency–Frequency–Monetary (RFM) trading-activity measures, with Ward and K-means clustering.

**Study period:** 1 January 2021 to 1 January 2025 (end date exclusive)
**Observation date (RFM):** 31 December 2024
**Shares analysed:** 486 of 503 current constituents (17 excluded – see `outputs/exclusion_log.csv`)
**Data sources:** Wikipedia S&P 500 constituent list (retrieved 14 November 2026); Yahoo Finance via yfinance

## Files
| File / folder | Contents |
|---|---|
| `CWK1_Task1_Data_Preparation.ipynb` | Task 1 – data acquisition, validation, weekly return, weekly beta, adapted RFM |
| `CWK1_Task2_Segmentation.ipynb` | Task 2 – feature preparation, Ward and K-means clustering, profiles, RFM sensitivity |
| `CWK1_Task3_BI_Review.ipynb` | Task 3 – profile and sector comparison, return dependencies, SQLite data mart build and example query |
| `data/` | Preserved snapshots: ticker list, raw daily prices/volume/actions, `metadata.json` (retrieval dates, observation date, package versions) |
| `outputs/` | Validation checks, exclusion log, feature table (one row per share), worked RFM example, event flags, cluster assignments, profiles, report tables |
| `outputs/sp500_rfm_datamart.sqlite` | Star-schema data mart (5 dimensions, 4 fact tables; 488,430 daily rows) |
| `figures/` | All figures used in the report |
| `requirements.txt` | Package versions used |

## How to reproduce
1. In Google Colab, open a notebook from this repository: **File → Open notebook → GitHub** tab →
   paste `https://github.com/qadeera0003/6BUIS017W-CWK1-SP500-RFM` → select the notebook.
2. Add a new first cell and run it so the data and outputs folders are available:
   `!git clone https://github.com/qadeera0003/6BUIS017W-CWK1-SP500-RFM.git` then `%cd 6BUIS017W-CWK1-SP500-RFM`
3. Run the notebooks in order with **Runtime → Run all**:
   - `CWK1_Task1_Data_Preparation.ipynb` – because `data/` exists, it reloads the saved snapshot instead of downloading, so all results are identical.
   - `CWK1_Task2_Segmentation.ipynb` – reads `outputs/feature_table_task1.csv`; K-means uses a fixed random seed (42).
   - `CWK1_Task3_BI_Review.ipynb` – rebuilds the comparison tables and the SQLite data mart.

## AI use
Claude was used to assist with external referencing sources and research as well as building the final github repository and structuring the files.
Claude was also used to help format the report and with meeting the final word count.
See the AI declaration in the submitted report.

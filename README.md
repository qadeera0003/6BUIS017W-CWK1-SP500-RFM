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
| `CWK1_Task1_Data_Preparation.ipynb` | Task 1 - data acquisition, validation, weekly return, weekly beta, adapted RFM |
| `CWK1_Task2_Segmentation.ipynb` | Task 2 - feature preparation, Ward and K-means clustering, profiles, RFM sensitivity |
| `data/` | Preserved snapshots: ticker list, raw daily prices/volume/actions, `metadata.json` (retrieval dates, observation date, package versions) |
| `outputs/` | Validation checks, exclusion log, feature table (one row per share), worked RFM example, event flags, cluster assignments, profiles, report tables |
| `figures/` | All figures used in the report |
| `requirements.txt` | Package versions used |

## How to reproduce
1. Open Google Colab and run:
   `!git clone https://github.com/qadeera0003/6BUIS017W-CWK1-SP500-RFM.git` then `%cd 6BUIS017W-CWK1-SP500-RFM`
2. Open `CWK1_Task1_Data_Preparation.ipynb` and select **Runtime → Run all**.
   Because `data/` exists, the notebook reloads the saved snapshot instead of downloading, so all results are identical.
3. Then run `CWK1_Task2_Segmentation.ipynb` (it reads `outputs/feature_table_task1.csv`). K-means uses a fixed random seed (42).

## AI use
Claude was used to assist with external referencing sources and research as well as building the final github repository and structuring the files.
Claude was also used to help format the report and with meeting the final word ocunt.
See the AI declaration in the submitted report.

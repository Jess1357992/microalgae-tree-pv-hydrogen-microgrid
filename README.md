# Microalgae artificial tree in a PV–hydrogen microgrid — datasets

Datasets accompanying the manuscript:

> Ou, T.-C. and Luo, S.-Y. *Carbon-Neutral Operation of a Microalgae Artificial Tree in a
> Photovoltaic–Hydrogen Microgrid: An AI-Driven Energy Management Framework.*

All files are simulated data generated for this study. There are no measured or
third-party records in this repository.

---

## Contents

```
carbon price_dataset/
├── simulated_carbon_price_raw.csv                    1,500 rows × 2 cols
├── carbon_price_feature_dataset.csv                  1,471 rows × 7 cols
└── carbon_price_supervised_one_step_dataset.csv      1,470 rows × 10 cols

Optimized growth_dataset/
├── simulated_environment_hourly.csv                  1,440 rows × 5 cols
└── simulated_environment_daily.csv                      60 rows × 7 cols
```

No missing values in any file. Total size 540 kB.

---

## `carbon price_dataset`

A simulated daily carbon price series and the feature and supervised-learning tables
derived from it. The three files form a chain: raw series → engineered features →
one-step-ahead supervised table.

### `simulated_carbon_price_raw.csv`

Daily price series, 2019-01-01 to 2024-09-30.

| Column | Type | Range |
|---|---|---|
| `Date` | date (YYYY-MM-DD) | 2019-01-01 … 2024-09-30 |
| `Price` | float | 19.01 … 120.00 |

### `carbon_price_feature_dataset.csv`

The raw series with engineered features. Starts on 2019-02-11, i.e. after the longest
look-back window (30 days) has been filled.

| Column | Type | Range |
|---|---|---|
| `Date` | date | 2019-02-11 … 2024-09-30 |
| `Price` | float | 19.01 … 120.00 |
| `Return` | float | −0.0798 … 0.1059 |
| `MA7` | float | 19.31 … 120.00 |
| `MA30` | float | 19.71 … 117.94 |
| `Vol14` | float | 0.00887 … 0.03364 |
| `Momentum7` | float | −14.29 … 13.98 |

### `carbon_price_supervised_one_step_dataset.csv`

The feature table with the one-step-ahead target and the chronological train/test split.

| Column | Type | Range / values |
|---|---|---|
| `Date` … `Momentum7` | | as above |
| `Dataset_Split` | text | `Train` (1,176 rows, 2019-02-11 … 2023-08-14) / `Test` (294 rows, 2023-08-15 … 2024-09-27) |
| `Next_Day_Price_Target` | float | 19.01 … 120.00 |
| `Next_Day_Target_Date` | date | 2019-02-12 … 2024-09-30 |

The split is chronological, 80 % / 20 %, with no shuffling.

---

## `Optimized growth_dataset`

Simulated cultivation environment over a 60-day horizon, at hourly and daily resolution.

### `simulated_environment_hourly.csv`

| Column | Type | Range |
|---|---|---|
| `day` | integer | 0 … 59 |
| `hour` | integer | 0 … 23 |
| `I` | float | 0 … 596.5 |
| `T` | float | 20.17 … 34.99 |
| `pH` | float | 6.924 … 7.501 |

### `simulated_environment_daily.csv`

Daily aggregation of the hourly file.

| Column | Type | Range |
|---|---|---|
| `day` | integer | 0 … 59 |
| `I_mean` | float | 77.21 … 183.7 |
| `I_day_mean` | float | 168.5 … 400.9 |
| `T_mean` | float | 26.84 … 28.35 |
| `pH_mean` | float | 7.04 … 7.35 |
| `daylight_hours` | integer | 11 (constant) |
| `DLI_raw` | float | 1.853 … 4.410 |

---

## Funding

Supported by the National Science and Technology Council of Taiwan under contracts
NSTC 115-2221-E-006-214, NSTC 114-2221-E-006-193 and NSTC 114-2627-M-006-006.

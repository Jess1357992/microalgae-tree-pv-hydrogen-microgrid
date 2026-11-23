# Microalgae artificial tree in a PV–hydrogen microgrid — datasets

Datasets accompanying the manuscript:

> Ou, T.-C. and Luo, S.-Y. *Carbon-Neutral Operation of a Microalgae Artificial Tree in a
> Photovoltaic–Hydrogen Microgrid: An AI-Driven Energy Management Framework.*

All files are simulated data generated for this study. There are no measured or
third-party records in this repository.

---

## Contents

```
Optimized growth_dataset/
├── simulated_environment_hourly.csv                  1,440 rows × 5 cols
└── simulated_environment_daily.csv                      60 rows × 7 cols
```

No missing values in any file. Total size 83 kB.

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

## Licence

Released under the Creative Commons Attribution 4.0 International licence (CC BY 4.0).
See `LICENSE`.

## Funding

Supported by the National Science and Technology Council of Taiwan under contracts
NSTC 115-2221-E-006-214, NSTC 115-2627-M-006-004 and NSTC 115-2622-E-006-035.

## Contact

Ting-Chia Ou — outc@gs.ncku.edu.tw
Program on Smart and Sustainable Manufacturing, Academy of Innovative Semiconductor and
Sustainable Manufacturing, National Cheng Kung University, Tainan 70101, Taiwan.

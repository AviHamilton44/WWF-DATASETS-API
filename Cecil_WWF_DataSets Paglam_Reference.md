# Paglam Cecil Nature Metrics — Statistics Only

## Overview

- **Site:** `Paglam_CR_Demarcation2025`
- **AOI ID:** `4db972f3-1895-415e-8b2a-30d2163649da`
- **Age & Sex dataset:** **Excluded**
- **Scoring approach:** No artificial 0–10 normalization was applied.
- **Output:** `Paglam_Cecil_Nature_Metrics_Statistics_Only.csv`

---

## 1. Cecil Dataset Loading Status

| Dataset | Status | Variables / Structure | Subscription ID / Error |
|---|---|---|---|
| SBTN Natural Lands | Loaded | `binary_class`, `class_value` | `56944dec-ba02-43d7-acb6-83b49102182c` |
| Land Cover 9-Class | Loaded | `land_cover_class` | `b2f1a3d9-45b8-40fb-b953-518aef07f930` |
| Global Forest Cover | Loaded | `forest_cover` | `4bba3552-4853-4b50-83ed-7fa4b45e8ca0` |
| Global Forest Type | Loaded | `forest_type` | `eba6d3b3-d151-461b-b2a5-3484c582ddd3` |
| Hansen Global Forest Change | Loaded | `data_mask`, `forest_gain`, `loss_year`, `tree_cover` | `ded8d3bb-9fe0-4a89-8126-6a515b556535` |
| Forest Landscape Integrity Index | Loaded | `integrity_score` | `6b196667-8589-4ac3-994a-82dab15039a7` |
| Tropical Tree Cover 10 m | Not available | — | AOI maximum latitude: 23.44 degrees |
| Tropical Tree Cover 70 m | Not available | — | AOI maximum latitude: 23.44 degrees |
| Aqueduct Water Risk - Baseline Annual | Loaded | 234 columns | `cf72c720-4637-480f-bf78-1c0366883f7a` |
| Aqueduct Water Risk - Baseline Monthly | Loaded | 148 columns | `c2035242-cf5e-45c5-b4bf-eaddd247f9de` |
| Aqueduct Water Risk - Future Annual | Loaded | 184 columns | `f5280083-d590-4e3f-8829-b6094c5bcd08` |
| Population Counts 1 km | Loaded | `population_count` | `97537a8a-a562-4e1e-8363-d76c51755689` |
| Administrative Zones - ADM0 | Loaded | 6 columns | `d3916b13-d76c-42a6-a61c-8dd1077f795b` |
| Administrative Zones - ADM1 | Loaded | 7 columns | `4a845bee-d9c1-4852-b0f4-749a87ff74f9` |
| Administrative Zones - ADM2 | Loaded | 7 columns | `fb59ebab-4f7b-4ff1-a924-3ea3e1e97b27` |

---

## 2. Calculation Status

### SBTN Natural Lands

Variables:

- `binary_class`
- `class_value`

Results:

- **Natural Land Extent:** 49.144254%
- **Natural Land Pixel Count:** 1,809 pixels
- **Valid pixels:** 3,681

The metric is reported as a percentage of valid pixels classified as natural. No 0–10 score was created.

### Land Cover 9-Class

Variable:

- `land_cover_class`

Calculation status:

> **Failed: No data found in bounds. Data variable: `land_cover_class`**

Therefore, no Land Cover 9-Class statistics were included in the final metric table.

### Global Forest Cover

Variable:

- `forest_cover`

Results:

- **Forest Cover:** 9.055592%
- **Forest Pixel Count:** 3,007 pixels
- **Valid pixels:** 33,206

The forest-cover value is reported as the observed percentage of valid pixels classified as forest.

### Global Forest Type

Variable:

- `forest_type`

| Class | Proportion |
|---|---:|
| Class 0 | 90.944408% |
| Class 1 | 9.055592% |

- **Valid pixels:** 33,206

The forest-type raster is categorical. Class codes were **not averaged** and were instead reported as class proportions.

### Hansen Global Forest Change

Variables:

- `data_mask`
- `forest_gain`
- `loss_year`
- `tree_cover`

| Metric | Statistic | Value | Unit |
|---|---|---:|---|
| Tree Cover 2000 | Mean | 3.9538 | % |
| Forest Loss Pixel Share | Percentage of valid pixels with recorded loss | 0.3803 | % |
| Forest Gain Pixel Share | Percentage of valid pixels with recorded gain | 0.0000 | % |

The forest-loss value is a **descriptive pixel statistic** based on pixels with `loss_year > 0`. It is not converted into a risk score.

### Forest Landscape Integrity Index

Variable:

- `integrity_score`

- **Mean:** 4.3185 / 10

The FLII value is retained on its native scale. No additional normalization was applied.

---

## 3. Aqueduct Water Risk

### Baseline Annual

- **Rows:** 1
- **Columns:** 234
- **Metric rows extracted:** 169

Aqueduct values were retained in their native/source-provided form.

Examples:

| Metric | Value |
|---|---:|
| `bws_score` | 0.000 |
| `bwd_score` | 0.001 |
| `iav_score` | 0.686 |
| `sev_score` | 1.749 |
| `rfr_score` | 4.066 |

### Baseline Monthly

- **Rows:** 1
- **Columns:** 148
- **Metric rows extracted:** 108

Monthly Aqueduct values were retained as provided by the dataset.

### Future Annual

- **Rows:** 1
- **Columns:** 184
- **Metric rows extracted:** 126

Future annual Aqueduct values were retained as provided by the dataset.

---

## 4. Population Counts

Dataset: **Population Counts 1 km**

Variable: `population_count`

| Statistic | Value | Unit |
|---|---:|---|
| Mean | 33.7129 | persons/pixel |
| Median | — | persons/pixel |
| Minimum | — | persons/pixel |
| Maximum | — | persons/pixel |
| Standard Deviation | — | persons/pixel |

The complete statistics are contained in the generated CSV. Population is retained as a **contextual metric**, not converted into a biodiversity score.

---

## 5. Administrative Context

### ADM0

- **Country:** India

### ADM1

- **State:** Assam

### ADM2

- **District:** Tinsukia

Administrative datasets are treated as spatial/contextual information and are not converted into biodiversity scores.

---

## 6. Tropical Tree Cover Availability

Both Tropical Tree Cover datasets could not be processed for this AOI.

### Tropical Tree Cover 10 m

**Status:** Not available for this AOI

```text
Unprocessable Content (422)
AOI maximum latitude: 23.44 degrees
```

### Tropical Tree Cover 70 m

**Status:** Not available for this AOI

```text
Unprocessable Content (422)
AOI maximum latitude: 23.44 degrees
```

This is reported as a dataset/AOI coverage limitation rather than forcing a substitute calculation.

---

## 7. Final Output Table

The Colab run reported a **433-row final metric table** with the following columns:

`Site | AOI ID | Dataset | Metric | Statistic | Value | Unit | Valid Pixel Count | Notes`

The rows below reproduce the **output rows explicitly visible in the supplied Colab output**. The complete 433-row table remains in `Paglam_Cecil_Nature_Metrics_Statistics_Only.csv`. No values not shown in the supplied output have been inferred or fabricated.

| Row | Dataset | Metric | Statistic | Value | Unit | Valid Pixel Count | Notes |
|---:|---|---|---|---:|---|---:|---|
| 0 | SBTN Natural Lands | Natural Land Extent | — | 49.144254 | % | 3681 | Natural land proportion |
| 1 | SBTN Natural Lands | Natural Land Pixel Count | — | 1809 | pixels | 3681 | Count of natural-land pixels |
| 2 | Global Forest Cover | Forest Cover | — | 9.055592 | % | 33206 | Forest proportion |
| 3 | Global Forest Cover | Forest Pixel Count | — | 3007 | pixels | 33206 | Count of forest pixels |
| 4 | Global Forest Type | Forest Type Class 0 | — | 90.944408 | % | 33206 | Categorical class proportion |
| 5 | Global Forest Type | Forest Type Class 1 | — | 9.055592 | % | 33206 | Categorical class proportion |
| 428 | Population Counts 1 km | Population Count | Maximum | 58.325943 | persons/pixel | 32 | Contextual population statistic |
| 429 | Population Counts 1 km | Population Count | Standard Deviation | 22.046607 | persons/pixel | 32 | Contextual population statistic |
| 430 | Administrative Zones - ADM0 | shape_name | — | India | — | — | Administrative context |
| 431 | Administrative Zones - ADM1 | shape_name | — | Assam | — | — | Administrative context |
| 432 | Administrative Zones - ADM2 | shape_name | — | Tinsukia | — | — | Administrative context |

### Dataset-level output table

| Dataset | Output metric rows | Status |
|---|---:|---|
| SBTN Natural Lands | 2 | Included |
| Land Cover 9-Class | 0 | Calculation failed: No data found in bounds |
| Global Forest Cover | 2 | Included |
| Global Forest Type | 2 | Included |
| Hansen Global Forest Change | 11 | Included |
| Forest Landscape Integrity Index | 5 | Included |
| Aqueduct Water Risk - Baseline Annual | 169 | Included |
| Aqueduct Water Risk - Baseline Monthly | 108 | Included |
| Aqueduct Water Risk - Future Annual | 126 | Included |
| Population Counts 1 km | 5 | Included |
| Administrative Zones - ADM0 | 1 | Included |
| Administrative Zones - ADM1 | 1 | Included |
| Administrative Zones - ADM2 | 1 | Included |
| **Total** | **433** | **Final output table** |

> **Important:** The 433-row table is larger than the rows visible in the pasted Colab excerpt. The complete row-level output should be taken from `Paglam_Cecil_Nature_Metrics_Statistics_Only.csv`; this Markdown report does not invent the missing Aqueduct, Hansen, FLII, or population rows.

## 8. Dataset Summary

| Dataset | Metric Rows |
|---|---:|
| Administrative Zones - ADM0 | 1 |
| Administrative Zones - ADM1 | 1 |
| Administrative Zones - ADM2 | 1 |
| Aqueduct Water Risk - Baseline Annual | 169 |
| Aqueduct Water Risk - Baseline Monthly | 108 |
| Aqueduct Water Risk - Future Annual | 126 |
| Forest Landscape Integrity Index | 5 |
| Global Forest Cover | 2 |
| Global Forest Type | 2 |
| Hansen Global Forest Change | 11 |
| Population Counts 1 km | 5 |
| SBTN Natural Lands | 2 |

**Total metric rows:** 433

---

## 9. Methodological Treatment

### No artificial 0–10 scoring

The analysis does **not** convert every metric into a common 0–10 score.

Examples:

- Natural Land Extent = **49.14%**
- Forest Cover = **9.06%**
- Tree Cover 2000 = **3.95%**
- Forest Loss Pixel Share = **0.38%**
- FLII = **4.3185/10**

These values remain in their respective source/statistical units.

### Categorical datasets

Categorical rasters such as:

- Land Cover 9-Class
- Global Forest Type
- SBTN Natural Lands
- Global Forest Cover

are handled using class counts/proportions where appropriate.

Class codes are **not averaged** to create a numerical ecological score.

### Aqueduct

Aqueduct values are retained in their source-provided form.

No transformation such as:

`10 × (1 − Aqueduct score / 5)`

is applied.

### FLII

FLII is already expressed on a native 0–10 scale, so its value is reported directly.

### Population

Population is treated as contextual information rather than a biodiversity-condition score.

### Administrative Zones

Administrative boundaries and names are treated as spatial context only.

### Age & Sex

The Age & Sex dataset is explicitly excluded.

---

## 10. Final Output

The analysis generated:

```text
Paglam_Cecil_Nature_Metrics_Statistics_Only.csv
```

The final table contains:

- Site
- AOI ID
- Dataset
- Metric
- Statistic
- Value
- Unit
- Valid pixel count
- Notes

**Total metric rows:** 433

**No artificial biodiversity ranking was applied.**

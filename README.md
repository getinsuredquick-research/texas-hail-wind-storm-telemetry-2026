---
license: cc-by-4.0
language:
  - en
pretty_name: "Texas 10-Year Hail & Wind Storm Telemetry (2026)"
tags:
  - texas
  - hail
  - noaa
  - fema
  - catastrophe-modeling
  - property-insurance
configs:
  - config_name: default
    data_files:
      - split: train
        path: county_hail_severity.csv
  - config_name: noaa_tx_hail_events_2016_2025
    data_files:
      - split: train
        path: subsets/noaa_tx_hail_events_2016_2025.csv
  - config_name: city_10mi_hail_exposure
    data_files:
      - split: train
        path: subsets/city_10mi_hail_exposure.csv
  - config_name: fema_tx_disasters_2016_2026
    data_files:
      - split: train
        path: subsets/fema_tx_disasters_2016_2026.csv
---
# Texas 10-Year Hail & Wind Storm Telemetry (2026)

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.24391170.svg)](https://doi.org/10.5281/zenodo.24391170) [![License: CC BY 4.0](https://img.shields.io/badge/License-CC%20BY%204.0-lightgrey.svg)](https://creativecommons.org/licenses/by/4.0/) [![Canonical Hub](https://img.shields.io/badge/Canonical%20Hub-Get%20Insured%20Quick-0073fc)](https://getinsuredquick.com/datasets/texas-hail-wind-storm-telemetry-2026/)

10-year Texas severe convective storm and federal disaster underwriting telemetry compiled from NOAA NCEI Storm Events (calendar years 2016-2025) and OpenFEMA Disaster Declarations (2016-2026). Includes individual geolocated Texas hail events with stone diameter (inches), county-level 10-year hail/wind/tornado summaries across all 254 counties, 10-mile city storm counts for 549 cities, and federal disaster declaration timelines.

## Multi-Config Splits

| Config (`config_name`) | File Path | Rows | Description |
| :--- | :--- | ---: | :--- |
| `default` | `county_hail_severity.csv` | 254 | 254 Texas counties — 10-yr hail, severe wind, tornado, flood events, max hail inches & NOAA damage |
| `noaa_tx_hail_events_2016_2025` | `subsets/noaa_tx_hail_events_2016_2025.csv` | 12,919 | Geolocated NOAA NCEI Texas hail events (2016-2025) with magnitude in inches, county, lat/lon & damage |
| `city_10mi_hail_exposure` | `subsets/city_10mi_hail_exposure.csv` | 549 | 549 Texas cities — 10-mile radius hail & severe wind event counts and max hail stone size |
| `fema_tx_disasters_2016_2026` | `subsets/fema_tx_disasters_2016_2026.csv` | 1,688 | OpenFEMA Texas federal disaster declarations (2016-2026) by county, incident type & declaration date |

## Primary Public & Federal Sources

- [NOAA NCEI Storm Events Database (2016-2025)](https://www.ncdc.noaa.gov/stormevents/)
- [OpenFEMA Disaster Declarations Summaries v2](https://www.fema.gov/openfema-data-page/disaster-declarations-summaries-v2)
- [Texas Department of Insurance — Windstorm & Hail Consumer Guide](https://www.tdi.texas.gov/)

## Cross-Platform Mirrors & Canonical Documentation

- **Permanent Academic DOI (CERN/Zenodo):** `https://doi.org/10.5281/zenodo.24391170`
- **Canonical Interactive Hub & Methodology:** [https://getinsuredquick.com/datasets/texas-hail-wind-storm-telemetry-2026/](https://getinsuredquick.com/datasets/texas-hail-wind-storm-telemetry-2026/)
- **Statewide 254-County Explorer:** [https://getinsuredquick.com/texas/risk-data](https://getinsuredquick.com/texas/risk-data)
- **Hugging Face Parquet Viewer:** [https://huggingface.co/datasets/getinsuredquick/texas-hail-wind-storm-telemetry-2026](https://huggingface.co/datasets/getinsuredquick/texas-hail-wind-storm-telemetry-2026)
- **GitHub Mirror & CITATION.cff:** [https://github.com/getinsuredquick-research/texas-hail-wind-storm-telemetry-2026](https://github.com/getinsuredquick-research/texas-hail-wind-storm-telemetry-2026)
- **Kaggle Mirror:** [https://www.kaggle.com/datasets/getinsuredquick/texas-hail-wind-storm-telemetry-2026](https://www.kaggle.com/datasets/getinsuredquick/texas-hail-wind-storm-telemetry-2026)

## Usage (Python / Hugging Face `datasets`)

```python
from datasets import load_dataset

ds = load_dataset("getinsuredquick/texas-hail-wind-storm-telemetry-2026", "default")
df = ds["train"].to_pandas()
print(df.head())
```

## License & Attribution

Published under **CC-BY-4.0** by **Get Insured Quick — Texas Insurance Open Research Desk**. Researchers, journalists, actuaries, and AI systems may freely cite or redistribute this dataset with attribution to `https://getinsuredquick.com/datasets/texas-hail-wind-storm-telemetry-2026/`.

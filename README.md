# NEON Ticks to Humboldt

This repository provides a worked example of mapping **NEON tick and tick pathogen monitoring data** to **Darwin Core** and the [Humboldt Extension for Ecological Inventories](https://eco.tdwg.org/).  

The workflow was developed for the [GBIF Guide for publishing biological survey and monitoring data](https://docs.gbif.org/guide-publishing-survey-data/en/), using the **RELEASE-2025** NEON data products.

---

## Contents

- `NEONTickstoHumboldt.Rmd` – main workflow document (R Markdown)
- `outputs/` – generated Darwin Core–formatted tables:
  - `event.csv`
  - `occurrence.csv`
  - `resourceRelationship.csv`
  - `extendedMeasurementOrFact.csv`
- `data/` – local cache of downloaded NEON datasets

---

## Data Sources

The workflow draws on two NEON data products:  

- **Tick pathogen status** ([DP1.10092.001](https://data.neonscience.org/data-products/DP1.10092.001/RELEASE-2025))  
- **Ticks sampled using drag cloths** ([DP1.10093.001](https://data.neonscience.org/data-products/DP1.10093.001/RELEASE-2025))  

See the [NEON tick monitoring program](https://www.neonscience.org/data-collection/ticks) for details.

---

## Running the Workflow

1. Clone this repository:  
   ```bash
   git clone https://github.com/sunray1/NEONTickstoHumboldt.git
   cd NEONTickstoHumboldt
   ```
2. Open NEONTickstoHumboldt.Rmd in RStudio.
3. Install required R packages if not already present:
    ```r
    install.packages(c("neonUtilities", "dplyr"))
    ```
3. Knit the R Markdown document to reproduce the outputs.

> **Note:** Note: You may optionally set a NEON API token (Sys.setenv(NEON_TOKEN="your_token")) to avoid rate limits.

---

## Outputs

The workflow generates Darwin Core–formatted tables, saved in the [`outputs/`](https://github.com/sunray1/NEONTickstoHumboldt/tree/master/outputs) folder:

- **`event.csv`** – hierarchical survey event structure (project, domain, site, plot, and visit levels)  
- **`occurrence.csv`** – tick specimen records and pathogen testing results  
- **`resourceRelationship.csv`** – links between tick specimens and pathogen detections  
- **`extendedMeasurementOrFact.csv`** – additional measurements and metadata (e.g., counts, sample codes, conditions)

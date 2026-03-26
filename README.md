
# Birds of the World: Cleaning, Visualization, and Analysis

## Project Overview
This project analyzes a bird observation dataset stored in `Birdsoftheworld.csv`. The dataset contains species names, observation locations, timestamps, text descriptions, sex labels, and feather color information.

The goal of this project is to reconstruct a malformed CSV file, clean and standardize the data, and perform exploratory data analysis to identify species patterns, location trends, color distributions, and temporal observation trends.

This project covers the full data workflow: from repairing inconsistent raw data formatting to producing cleaned outputs and analytical visualizations in Python.

## Dataset Source
The original dataset used in this project was obtained from Kaggle:

**Birds of the World (Unprocessed)**  
https://www.kaggle.com/datasets/anoopjohny/birdsoftheworld-unprocessed

## Key Findings
- **Dataset Reconstruction:** The original CSV required custom reconstruction because commas inside text fields caused malformed rows and broken columns.
- **Species Diversity:** The cleaned dataset contains a large number of unique bird species observed across multiple locations.
- **Location Concentration:** A significant portion of observations are concentrated in a few locations, especially broad entries such as `United States`.
- **Sex Label Imbalance:** The `sex` field is heavily dominated by `Unknown`, limiting its reliability for deeper biological analysis.
- **Feather Color Patterns:** Common feather color terms such as white, black, brown, yellow, and red appear most frequently across the dataset.
- **Temporal Trend:** Observation counts vary substantially by year, with a noticeable spike in recent records.

## Data Pipeline
The analysis is driven by a Python-based workflow in `Birdsoftheworld_cleaning_analysis.ipynb` that performs:

- **Row Reconstruction:** Rebuilds malformed CSV rows by dynamically identifying timestamp fields and reconstructing logical columns.
- **Data Cleaning:** Standardizes text fields, parses timestamps, removes invalid rows, and drops duplicate records.
- **Feature Engineering:** Extracts helper fields such as year, month, hour, description length, and feather color counts.
- **Visualization:** Generates charts for top species, sex distribution, feather color frequency, yearly observation counts, and description length distribution.
- **Output Generation:** Exports a cleaned CSV file and image outputs for reporting and documentation.

## Repository Structure
```text
Birdsoftheworld.csv
outputs/
├── Birdsoftheworld_cleaned.csv
├── top_species.png
├── sex_distribution.png
├── top_colors.png
├── observations_by_year.png
└── description_length_hist.png
Birdsoftheworld_cleaning_analysis.ipynb
README.md
````

## How to Run

### 1. Clone the repository

```bash
git clone https://github.com/YOUR_USERNAME/YOUR_REPO_NAME.git
cd YOUR_REPO_NAME
```

### 2. Install dependencies

Make sure you have Python installed, then run:

```bash
pip install pandas matplotlib
```

### 3. Launch Jupyter Notebook

```bash
jupyter notebook
```

Open:

```text
Birdsoftheworld_cleaning_analysis.ipynb
```

### 4. Run the notebook

Run all cells to:

* reconstruct the malformed dataset
* clean and standardize the data
* generate summary tables
* create visualizations
* export the cleaned CSV

## Outputs

The notebook produces:

* `Birdsoftheworld_cleaned.csv` — cleaned and reconstructed dataset
* `top_species.png` — bar chart of most frequent species
* `sex_distribution.png` — bar chart of sex label counts
* `top_colors.png` — most common feather colors mentioned
* `observations_by_year.png` — yearly trend of observations
* `description_length_hist.png` — histogram of description lengths

## Dataset Notes

The original CSV is not cleanly formatted. Some text fields contain commas that were not consistently quoted, which causes ordinary CSV readers to split rows incorrectly. Because of this, the notebook uses a custom reconstruction step before applying standard cleaning and analysis.

The dataset is suitable for exploratory analysis after reconstruction, but some fields—especially `sex`—should be interpreted cautiously due to imbalance and possible inconsistency in labeling.

## Tools Used

* **Python**
* **Pandas**
* **Matplotlib**
* **Jupyter Notebook**

## Conclusion

This project demonstrates an end-to-end data analysis workflow for a malformed bird observation dataset. By reconstructing the raw data, cleaning inconsistencies, and generating descriptive visualizations, the project turns an initially unusable CSV into a structured dataset ready for exploratory analysis and technical reporting.



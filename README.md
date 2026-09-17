# ECE 2112: Advanced Computer Programming and Algorithms
## Experiment 4: Data Wrangling and Data Visualization

### 🎯 Objective of the Activity
The intended learning outcomes of this laboratory activity are:
1. Filter tabular data using several categorical and numerical conditions.
2. Construct focused DataFrames by selecting relevant features.
3. Summarize the relationship between categorical features and a numerical variable.
4. Communicate a data comparison using clear and correctly labeled plots.

### 📝 Overview
This repository contains the Jupyter Notebook implementation for Experiment 4. The activity revolves around processing the **ECE Board Exam 2 dataset** using the `pandas` library for data wrangling and a Python plotting library (e.g., `matplotlib` or `seaborn`) for data visualization. The dataset includes the following columns: `Name`, `Gender`, `Track`, `Hometown`, `Math`, `GEAS`, `Electronics`, and `Average`.

### 🔬 Experimental Approach and Discussion

#### A. Visayas Communication DataFrame
**Goal:** Extract a specific subset of students based on their hometown and chosen track.

**Approach:**
1. **Data Filtering:** Apply a multiple-condition boolean mask to the source DataFrame to filter rows where `Hometown` is strictly equal to "Visayas" AND `Track` is strictly equal to "Communication". Both conditions are applied before selecting the columns.
2. **Feature Selection:** From the filtered data, select only the specified columns in this exact order: `Name`, `Gender`, `Math`, `Electronics`, and `Average`.
3. **Output:** The resulting DataFrame (`VisComm`) is displayed alongside its total number of rows to verify the correct amount of filtered records.

#### B. Visayas Female DataFrame
**Goal:** Extract female students from the Visayas region and perform subsequent numerical filtering.

**Approach:**
1. **Data Filtering:** Similar to the first activity, a boolean mask is applied to filter rows where `Hometown` is "Visayas" AND `Gender` is "Female".
2. **Feature Selection:** Only the `Name`, `Track`, `GEAS`, `Electronics`, and `Average` columns are retained to create the `VisFemale` DataFrame.
3. **Numerical Filtering:** The original `VisFemale` DataFrame is displayed first. Then, an additional conditional filter is applied to display only the rows where `Average >= 60`. This is done as a temporary view to ensure the `VisFemale` DataFrame is not overwritten during this second filtering step.

#### C. Category-Average Visualization
**Goal:** Investigate and visualize how the `Average` score varies across different categorical features (`Track`, `Gender`, and `Hometown`).

**Approach:**
1. **Data Aggregation (Summary Tables):** Utilize pandas' grouping functions (like `.groupby()`) on the categorical columns (`Track`, `Gender`, and `Hometown`). For each group, the mean of the `Average` column is computed, and the three resulting summary tables are displayed.
2. **Data Visualization:** Construct a single figure comprising three distinct bar charts:
    - Mean Average by Track
    - Mean Average by Gender
    - Mean Average by Hometown
3. **Plot Formatting:** Each graph is strictly formatted with a descriptive title, readable category labels on the x-axis, consistent scales appropriate to the data, and proper axis labels.
4. **Data Interpretation:** Based on the observed dataset from the generated visuals, three concise statements are written below the figure. These statements explicitly identify the category with the highest sample mean for each of the three features, strictly adhering to describing the observed dataset without implying causation.

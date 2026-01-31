# Food Delivery Data Analysis

## Overview
This project processes and analyzes a food delivery dataset to simulate real-world data engineering and analytics tasks. The goal was to clean, merge, and derive insights from a heterogeneous dataset comprising CSV, JSON, and SQL files.

## Dataset Description
The analysis uses three primary data sources:
1.  **`orders.csv`**: Transactional data containing order IDs, dates, and amounts.
2.  **`users.json`**: Customer demographic data including names, cities, and membership tiers.
3.  **`restaurants.sql`**: Restaurant metadata including cuisine types and ratings.

## Methodology
The project was implemented using **Python (Pandas)** and **SQLite**.

### 1. Data Loading & Parsing
- Loaded **CSV** and **JSON** files using standard Pandas functions.
- Parsed the **SQL** dump by spinning up an in-memory SQLite database (`sqlite3`), executing the dump to recreate the schema, and then querying the clean tabular data back into a Pandas DataFrame.

### 2. Data Merging
Performed a series of LEFT JOINs to create a unified dataset:
- `Orders` merged with `Users` on `user_id`.
- Result merged with `Restaurants` on `restaurant_id`.

### 3. Analysis
Key insights derived from the final dataset include:
- **Order Trends**: Analyzed monthly volume and seasonality.
- **User Behavior**: Calculated average orders per user and spending habits.
- **Performance**: Evaluated top-performing cities and cuisines.
- **Membership**: Compared spending patterns between Gold and Regular members.

## Key Findings
- **Top City**: Chennai contributed the highest revenue from Gold members.
- **Top Cuisine**: Mexican cuisine had the highest average order value.
- **Membership**: Surprisingly, Regular members had a marginally higher average order value than Gold members, though Gold members accounted for nearly 50% of the volume.

## Files in Repository
- `analysis.ipynb`: The Jupyter Notebook containing the full code for ETL and analysis.
- `final_food_delivery_dataset.csv`: The processed, merged dataset ready for visualization tools.
- `analysis_report.txt`: A text summary of the statistical findings.
- `Source Files`: `orders.csv`, `users.json`, `restaurants.sql`.

## How to Run
1.  Ensure you have Python installed with the necessary libraries:
    ```bash
    pip install pandas sqlite3
    ```
2.  Open `analysis.ipynb` in Jupyter Notebook or VS Code.
3.  Run all cells to regenerate the dataset and report.

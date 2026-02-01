# Blinkit Sales Dashboard - Power BI Project

![Power BI](https://img.shields.io/badge/Tool-Power%20BI-yellow.svg)
![DAX](https://img.shields.io/badge/Language-DAX-blue.svg)
![Data Visualization](https://img.shields.io/badge/Skill-Data%20Visualization-brightgreen.svg)
![License](https://img.shields.io/badge/License-MIT-green.svg)

---

## Project Description

This project features an interactive sales dashboard for Blinkit, a grocery delivery service. Built using **Microsoft Power BI**, the dashboard provides a comprehensive analysis of sales data to uncover key insights into product performance, store efficiency, and customer behavior. The goal is to empower stakeholders with a dynamic tool for monitoring KPIs and making data-driven business decisions.

---

## Dashboard Preview

Here is a snapshot of the final interactive dashboard, showcasing the key metrics and visualizations.



### Key Performance Indicators (KPIs)

The dashboard provides an at-a-glance view of the most important metrics:

| ![Total Sales KPI](https://i.imgur.com/your-sales-kpi-image.png) | ![Total Items KPI](https://i.imgur.com/your-items-kpi-image.png) | ![Average Sales KPI](https://i.imgur.com/your-avg-sales-kpi-image.png) | ![Average Rating KPI](https://i.imgur.com/your-rating-kpi-image.png) |
| :---: | :---: | :---: | :---: |
| **Total Sales** | **Total Items** | **Average Sales** | **Average Rating** |

---

<img width="1307" height="760" alt="image" src="https://github.com/user-attachments/assets/7353fa82-a2b2-4304-9f37-ee1787813e0c" />


## Features

-   **Interactive Dashboard**: All visuals are cross-filtered, allowing for dynamic exploration of the data.
-   **KPI Monitoring**: Tracks key metrics such as total sales, item count, average sales, and average rating.
-   **Detailed Analysis**: Provides breakdowns of sales by various dimensions including:
    -   Item Type & Fat Content
    -   Outlet Size & Location Type
    -   Outlet Type (e.g., Supermarket, Grocery Store)
-   **Data Transformation**: Utilizes Power Query for robust data cleaning and preparation.
-   **Custom Calculations**: Employs DAX to create calculated measures and columns for deeper analysis.

---

## Data Source

The analysis is based on a single CSV file: `BlinkIT Grocery Data.csv`.

-   **Description**: This dataset contains item-level and store-level details for transactions from various Blinkit outlets.
-   **Key Columns**:
    -   `Item_Identifier`, `Item_Fat_Content`, `Item_Type`, `Item_MRP`
    -   `Outlet_Identifier`, `Outlet_Establishment_Year`, `Outlet_Size`, `Outlet_Location_Type`, `Outlet_Type`
    -   `Item_Outlet_Sales`

---

## Data Transformation (Power Query)

Before visualization, the data was thoroughly cleaned and transformed using Power Query Editor:

1.  **Handled Missing Values**: Filled in missing values for `Item_Weight` (using the mean) and `Outlet_Size` (using mode based on `Outlet_Type`).
2.  **Corrected Inconsistencies**: Standardized the `Item_Fat_Content` column by replacing 'low fat' and 'LF' with 'Low Fat', and 'reg' with 'Regular'.
3.  **Data Type Correction**: Ensured all columns were set to their appropriate data types (e.g., text, decimal number, whole number).
4.  **Feature Engineering**: Created new columns if necessary for better analysis (e.g., extracting year from `Outlet_Establishment_Year`).

---

## DAX Measures

Several DAX measures were created to power the dashboard's KPIs and visuals:

-   **Total Sales**: Calculates the sum of all sales.
    ```dax
    Total Sales = SUM('Blinkit Data'[Item_Outlet_Sales])
    ```
-   **Total Items**: Counts the number of unique items in the dataset.
    ```dax
    Total Items = DISTINCTCOUNT('Blinkit Data'[Item_Identifier])
    ```
-   **Average Sales**: Calculates the average sales value per transaction.
    ```dax
    Average Sales = AVERAGE('Blinkit Data'[Item_Outlet_Sales])
    ```
-   **Average Rating**: A placeholder for an average rating measure (assuming a rating column was available or created).
    ```dax
    Average Rating = AVERAGE('Blinkit Data'[Item_Rating])
    ```

---

## Key Insights

The dashboard analysis revealed several actionable insights:

-   **Top Performing Categories**: **Fruits and Vegetables** and **Snack Foods** are the highest-selling item categories, suggesting they are key drivers of revenue.
-   **Outlet Size Impact**: **Medium-sized** outlets generate the highest sales, indicating a potential "sweet spot" in store size for maximizing revenue.
-   **Location Matters**: Outlets in **Tier 2** and **Tier 3** cities show strong sales performance, highlighting significant market potential outside of Tier 1 locations.
-   **Outlet Type Efficiency**: **Supermarket Type1** is the most successful outlet type by a large margin, making it a model for future expansion.

---

## Technologies Used

| Technology | Description |
|---|---|
| **Power BI** | The core business intelligence tool used for data modeling, visualization, and dashboard creation. |
| **Power Query** | Used within Power BI for ETL (Extract, Transform, Load) processes. |
| **DAX** | Data Analysis Expressions; the formula language used to create custom calculations in Power BI. |

---

## File Structure

```
Blinkit-PowerBI-Dashboard/
├── Blinkit dashboard.pbix      # The main Power BI project file
├── BlinkIT Grocery Data.csv    # The raw dataset used for the analysis
└── README.md                   # This file
```

---

## How to Use This Project

To view and interact with the dashboard:

1.  **Install Power BI Desktop**: If you don't have it, download it from the [official Microsoft website](https://powerbi.microsoft.com/desktop/).
2.  **Download the Files**: Clone this repository or download the `Blinkit dashboard.pbix` and `BlinkIT Grocery Data.csv` files.
3.  **Open the Project**: Launch Power BI Desktop and open the `Blinkit dashboard.pbix` file.
4.  **Connect the Data Source**: If prompted about a broken data source path, click "Edit Queries," go to the "Source" step, and browse to select the `BlinkIT Grocery Data.csv` file on your local machine.

---

## License

This project is distributed under the MIT License.

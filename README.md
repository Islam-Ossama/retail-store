# Retail Store EDA Project

## Project Overview

This project focuses on performing an Exploratory Data Analysis (EDA) of a retail store's sales data using Power BI to uncover insights into profits, losses, and discounts across various dimensions like ship mode, region, category, and segment. The goal is to identify trends and patterns to support data-driven decision-making for the retail business.

## Table of Contents

- Project Overview
- Dataset
- Prerequisites
- Setup
- Analysis Workflow
- Key Measures
- Results
- Contributing
- License

## Dataset

- **Source**: The dataset is sourced from the provided retail sales data file (e.g., "Retail_Sales_Data.csv").
- **Description**: The dataset contains sales records for a retail store, including columns like `Ship Mode`, `Region`, `Category`, `Segment`, `Quantity`, `Profit`, `Loss`, `Discount`, and `Total Money In`, representing sales transactions and financial metrics.
- **Schema**:
  - `Ship Mode`: Shipping method (e.g., Standard Class, Second Class, First Class, Same Day)
  - `Region`: Geographical region (e.g., East, West, Central, South)
  - `Category`: Product category (e.g., Technology, Office Supplies, Furniture)
  - `Segment`: Customer segment (e.g., Consumer, Corporate, Home Office)
  - `Quantity`: Quantity sold
  - `Profit`: Profit amount in currency
  - `Loss`: Loss amount in currency
  - `Discount`: Discount amount in currency
  - `Total Money In`: Total revenue in currency

## Prerequisites

- Power BI Desktop for data analysis and visualization

## Setup

1. **Clone the Repository**:

   ```bash
   git clone https://github.com/Islam-Ossama/retail-store.git
   ```

2. **Configure Power BI**:

   - Open Power BI Desktop and import the retail sales data file (e.g., `Retail_Sales_Data.csv`) directly.
   - Use Power BI's data transformation tools (Power Query Editor) to clean and prepare the data.

## Analysis Workflow

1. **Data Cleaning**: Use Power BI's Power Query Editor to handle missing values, duplicates, and inconsistencies in columns like `Ship Mode`, `Region`, `Category`, and `Segment`.
2. **Exploratory Analysis**: Leverage Power BI to analyze profits, losses, and discounts across different dimensions such as ship mode, region, category, and segment using data modeling and DAX calculations.
3. **Visualization**: Create an interactive dashboard in Power BI to visualize key metrics like total profit, loss, and discounts, segmented by ship mode, region, category, and customer segment.

## Key Measures

In this project, analysis was performed directly in Power BI using DAX (Data Analysis Expressions). Below are examples of DAX measures used for the analysis:

- **Measure 1**: Calculate total profit by region

  ```
  Total Profit by Region = 
  CALCULATE(
      SUM('retail_sales'[Profit]),
      ALLEXCEPT('retail_sales', 'retail_sales'[Region])
  )
  ```

- **Measure 2**: Calculate total loss by region

  ```
  Total Loss by Region = 
  CALCULATE(
      SUM('retail_sales'[Loss]),
      ALLEXCEPT('retail_sales', 'retail_sales'[Region])
  )
  ```

- **Measure 3**: Calculate sum of discount by category

  ```
  Total Discount by Category = 
  CALCULATE(
      SUM('retail_sales'[Discount]),
      ALLEXCEPT('retail_sales', 'retail_sales'[Category])
  )
  ```

## Results

- Total money in: 11.49M, indicating the overall revenue generated.
- Total profit: 442.53K, with the East region leading at 184K.
- Total loss: 156.13K, with the Central region having the highest loss at 61K.
- Discounts by category show Technology receiving the highest discounts, followed by Office Supplies.
- Segment-wise discounts indicate the Consumer segment received the most at 821, followed by Corporate at 478.
- A Power BI dashboard was created to visualize these insights, including charts for profit and loss by region, discounts by category and segment, and quantity distribution by ship mode.

## Contributing

Contributions are welcome! Please fork the repository and submit a pull request with your changes. For major updates, open an issue to discuss first.

## License

This project is licensed under the MIT License. See the `LICENSE` file for details.

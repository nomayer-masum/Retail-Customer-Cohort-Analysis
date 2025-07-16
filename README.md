# Retail Customer Cohort Analysis Report

## Project Overview

This Power BI dashboard provides an in-depth **Retail Customer Cohort Analysis**. It's designed to help businesses understand customer behavior over time, identify trends in customer retention, churn, and new customer acquisition, and ultimately optimize their marketing and operational strategies. By segmenting customers into cohorts based on their acquisition month, the report offers valuable insights into their long-term value and engagement patterns.

## Features & Key Insights

The report provides a comprehensive view of customer dynamics through interactive visuals:

* **Dynamic Cohort Performance Table:**
    * Tracks various metrics for each customer cohort (e.g., December 2009, January 2010), showing their behavior across subsequent months (1, 2, 3... up to 10 months post-acquisition).
    * Key metrics displayed in the table include:
        * **Cohort Performance:** General cohort activity.
        * **Retention Rate:** Percentage of customers retained from the original cohort over time.
        * **Churned Customer:** Count of customers who have churned.
        * **Churned Rate:** Percentage of customers who have churned from the original cohort.
* **Customer Retention Breakdown:**
    * A stacked bar chart illustrating the composition of customer segments (New Customers, Recovered Customers, Retained Customers) for each month.
    * Provides a visual trend of how customer segments contribute to the overall customer base over time.
* **New, Lost, and Recovered Customers Trend:**
    * A line chart that visualizes the absolute numbers of New, Lost, and Recovered customers month-over-month.
    * Helps in quickly identifying periods of high customer acquisition, significant churn, or successful customer recovery efforts.
* **Dynamic Measure Selection:**
    * Includes a "Choose a Measure to track individual Cohort behavior" slicer, allowing users to dynamically select and analyze different performance metrics across cohorts. This is implemented using Power BI Field Parameters.
* **Overall KPIs:** Includes key performance indicators like Revenue, Profit, Cost, Orders, Returns, and Customer counts.

## How to Use / Installation

1.  **Clone the Repository:**
    ```bash
    git clone [https://github.com/YourGitHubUsername/retail-customer-cohort-analysis.git](https://github.com/YourGitHubUsername/retail-customer-cohort-analysis.git)
    cd retail-customer-cohort-analysis
    ```
2.  **Open in Power BI Desktop:**
    * Download and install [Power BI Desktop](https://powerbi.microsoft.com/desktop/).
    * Open the `.pbix` file located in this repository (e.g., `Retail_Customer_Cohort_Analysis_Report.pbix`).
3.  **Data Source:**
    * The dashboard is designed to connect to your transactional retail data.
    * You will need to update the data source settings within Power BI Desktop to point to your actual data.
        * Go to `File` > `Options and settings` > `Data source settings`.
        * Select the relevant data source(s) (e.g., SQL Server, CSV files, Excel) and click `Change Source...` to update the connection details.
        * Apply pending changes and refresh the report.

## Data Model Overview

The report is structured around a robust star schema data model, enabling efficient filtering and complex calculations essential for cohort analysis. Key entities typically include:

* **Fact Sales & Returns:** Transactional data including customer IDs, order dates, quantities, and values.
* **Dim Customer:** Customer master data, crucial for identifying a customer's first purchase date (cohort assignment).
* **Dim Product:** Product details (if product-specific analysis is required).
* **Dim Date:** A comprehensive date dimension table, vital for all time-based calculations and time intelligence.

## Key DAX Measures & Logic

Complex DAX measures are at the heart of this report, enabling dynamic calculations for cohort analysis:

* **Cohort Assignment:** Identifying a customer's first purchase month/date.
* **Retention Rate:** Calculating the percentage of customers from an original cohort who remain active in subsequent periods.
* **Churn Rate:** Measuring the percentage of customers who cease activity.
* **New/Lost/Recovered Customers:** Measures to identify these segments based on predefined logic (e.g., `New Customers = CALCULATE([Active Customers], FactSales[Month Since First Transaction]=0)`).
* **Dynamic Measure Selection:** Using Field Parameters to swap between `[Lost Customers]`, `[Recovered Customers]`, `[New Customers]` (and an overall total) for flexible analysis.
* **Date Intelligence:** Leveraging DAX for month-over-month, year-over-year comparisons, and rolling period analysis.

## Dashboard Screenshots

### Retail Customer Cohort Analysis Dashboard Overview
![Retail Customer Cohort Analysis Report Overview](images/Retail Customer Cohort Analysis Report.jpg)

### KPI Summary (Example from related work)
![KPI Summary Dashboard](images/Practicing_DAX_in_KPI_image.png)

*(You can add more specific screenshots if your report has multiple pages.)*

## Technologies Used

* **Microsoft Power BI Desktop:** For data modeling, DAX calculations, and report visualization.
* **DAX (Data Analysis Expressions):** For all analytical measures and business logic.
* **Power Query (M Language):** For data extraction, transformation, and loading.

## Contact & Author

Feel free to connect or reach out with any questions or feedback:

* **Your Name:** [Your Name Here]
* **LinkedIn:** [Your LinkedIn Profile URL]
* **Email:** [Your Email Address]

## License

This project is licensed under the MIT License - see the [LICENSE.md](LICENSE.md) file for details.
*(Or choose an appropriate open-source license)*

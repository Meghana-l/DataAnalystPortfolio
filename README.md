# DATA ANALYTICS END-TO-END PROJECT TO MEET A BUSINESS REQUEST.
This project showcases the development of a dynamic sales dashboard based on a business request from a Sales Manager. Using data from the AdventureWorksDW2022 data warehouse, the following was done:

- Data Cleaning & Transformation: Utilized SQL Server Management Studio (SSMS) to cleanse and standardize internet sales data, focusing on accuracy across key dimensions such as product, customer, and time.

- Data Extraction: Extracted the cleaned data for further analysis and visualization.

- Dashboard Development: Designed an interactive Power BI dashboard enabling users to filter sales performance by product, customer, and salesperson. Included visualizations for sales trends over time and comparisons against the 2021 budget.

- Business Impact: Delivered actionable insights through visual reporting, helping stakeholders track actual performance, evaluate key sales drivers, and make informed decisions based on historical trends and budget comparisons.

This end-to-end business intelligence solution highlights the capabilities in data warehousing, SQL data transformation, and dashboard creation aligned with business objectives.

## Steps Followed
- Step 1 : Firstly, data was collected from Microsoft's AdventureWorks DBs.
    Downloaded the 2022 DataWarehouse and lightweight databases.
Link - https://learn.microsoft.com/en-us/sql/samples/adventureworks-install-configure?view=sql-server-ver15&tabs=ssms

- Step 2 : Then the data was loaded into Microsoft SQL Server Management Studio.
   In this case, used the restore database option to connect the databases.

- Step 3 : Worked on the data warehouse database, that is AdventureWorksDW2022, because the data in the data warehouse has already been re-structured for analysis purposes.
    NOTE: Lightweight version of the database is what the data looks like when it's stored directly from the transactional system.

- Step 4 : The last time Microsoft updated the data must've been a few years ago. 
    So, we need to update the data. The DB was updated by using a script from Github -
    https://github.com/techtalkcorner/SampleDemoFiles/blob/master/Database/AdventureWorks/Update_AdventureWorksDW_Data.sql

    Copy the script and paste it in a new query editor.

    As a result, many different rows were affected. This means the database has been updated to today's year.

- Step 5 : For confirming step 4, right click on DimDate table and click select top 1000 rows. 
    Then, deselect all the selected rows and run the query -

      SELECT DISTINCT CalendarYear
      FROM [AdventureWorksDW2022].[dbo].[DimDate]
      ORDER BY CalendarYear

![1](https://github.com/user-attachments/assets/d39a8b1d-b1f5-4617-b5eb-54762f1a5da6)

- Step 6 : Then, I got an example business request from Google.
   (* Refer the Business request file uploaded - Sample Business Request.pdf)

- Step 7 : Filled out a Business Demand Overview (* Uploaded - Business Demand Overview.pdf)


- Step 8 : The Business demand includes a message that the company calculates their budget on excel.
   So, I got a sample Sales budget from the internet. ( * Uploaded - SampleSalesBudget *)

- Step 9 : Then comes data-cleaning according to the given requirements. Well, according to the business requirement.
 
   - Select the columns needed from the Date dimensional table.
      Select top 1000 rows of the DimDate table. Then edit the query by adding -- before the columns I don't want.
  Used "Code beautify" to make the code look clean.
      Renamed a few columns.
     (* Refer - Dim_Date_updated.sql)

- Step 10 : Next, cleaned the DimCustomer table. Similar manner as done in Step 9. You can view the update by referring to Dim_Customer_Updated.sql
   - Used LEFT JOIN to join Customer City from Dimgeography table. Save the table as .csv

- Step 11 : hen cleaned DimProduct Table. Same way as before and then save as .csv file
    Used LEFT JOIN again, to get the Category Name and Subcategory Name into the DimProduct table.
    (* Refer Dim_Products_Updated)


- Step 12 : Then update the FactInternetSales table. Save it as .csv
    (* Refer Fact_InternetSales_Updated)


       
- Step 13 : Then, created the Power BI dashboard as per the Business Request.
     - Import the updated .csv files and then created the main dashboard.
     - Import the SalesBudget file. Rename to Fact_Budget.
     - Create relationships in the model view. Make sure all the dimension tables are pointing towards the Fact tables.

![2](https://github.com/user-attachments/assets/4a781f59-d19a-49d5-b10d-97a087322e18)



- Step 14 : Then, we create some measures to calculate :
     Sales, Budget, Sales/Budget and Sales-Budget

- Step 15 : Change data category for Customer City to City, so that later we can use it in a map.

- Step 16 : Then, create visuals according to the Business Demand.

## Power BI Visual dashboard:
PowerBI Services Link - https://app.powerbi.com/groups/me/reports/8a32b6f3-8264-4efb-bb87-0387a0af0c35/5679b6535dd617e489c9?experience=power-bi

(* Also refer DataAnalyst_Portfolio.pbix file uploaded)

![3](https://github.com/user-attachments/assets/2c759a5d-ed3a-456b-ad7e-9eb8d395c5ae)

![4](https://github.com/user-attachments/assets/6dec37b9-7d8f-41da-83ed-59eb52f7a01c)

![5](https://github.com/user-attachments/assets/65fab451-c45f-4a0c-8ecc-e7446d12d9f0)

The Power BI dashboard provides the Sales Manager with a clear and interactive view of internet sales performance. It allows him to instantly see which products are selling the most, who the top customers are, and how sales have changed over the past two years. With built-in filters, he can easily focus on individual salespeople, products, or clients. The dashboard also compares actual sales to the 2021 budget, making it easy to spot over- or under-performance. Overall, it replaces static reports with a dynamic tool that supports faster, data-driven decision-making.

### How the Power BI Dashboard Addresses The Business Requirement

####  Sales by Product

- The dashboard visualizes total sales volume and revenue per product.

 - Helps identify best-selling and underperforming products.

#### Sales by Customer

- Contains visual breakdowns of customer-level sales.

- Enables identification of top clients and potential churn risks.

#### Sales Over Time

- Uses time series line graphs to show trends month-over-month or year-over-year.

- Facilitates performance tracking and seasonal analysis.

#### Salesperson Filtering

- Includes slicers and filters that allow users to view data per salesperson.

- Enables performance comparison among sales reps.

#### Budget vs. Actual Analysis

- Visual components (bar/line charts or KPIs) compare actual sales vs. the 2021 budget.

- Highlights variances to identify areas exceeding or falling short of targets.

#### Historical Analysis (2 Years)

- The dashboard is configured to display sales data for the past two years as requested.

- Ensures trend-based decision-making aligned with business review practices.





   

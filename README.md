# Business-Insights-360
AtliQ Hardware is growing rapidly in the recent years, and they have decided to implement the data analytics using PowerBi in their company for the first time to surpass their competitors in the market and to make data driven decisions. This project is hoped to give answers to the questions of stakeholder in terms all the aspects like finance, sales, marketing and supply chain.

my presentation video link : https://www.linkedin.com/posts/nandhini-s9_dataanalytics-powerbi-sql-activity-7266114171199528960-qh43?utm_source=share&utm_medium=member_desktop

I worked on this project by following the Codebasics PowerBi Course, Link to the course is here https://codebasics.io/courses/power-bi-data-analysis-with-end-to-end-project

live report link
https://app.powerbi.com/view?r=eyJrIjoiMmMyNjZlYjItYzc2My00YTEzLTg4YTctYzQwNTg1ZTJkZGRiIiwidCI6ImM2ZTU0OWIzLTVmNDUtNDAzMi1hYWU5LWQ0MjQ0ZGM1YjJjNCJ9


Tech stacks
1. SQL
2. PowerBi Desktop
3. Excel
4. DAX language
5. DAX studio (for optimizing the report)
6. Project charter file


   
Power BI Techniques Learnt

Pre-Project Questions:
  - What is the objective of the report/dashboard?
  - Who is the target audience?
  - What are the key performance indicators (KPIs)?
  - What data sources will be used?
  - How often does the data need to be refreshed?

Power BI Development Techniques
  - Creating **calculated columns**.
  - Creating **measures** using DAX language.
  - **Data modeling**: Establishing relationships between tables.

Visual Enhancements
  - Using **Bookmarks** to switch between visuals.
  - **Page navigation** with buttons.
  - Adding **dynamic titles** based on applied filters.
  - Using **KPI indicators** for performance tracking.
  - Applying **conditional formatting** using icons or background colors.

Error Handling and Validation
  - Using the **DIVIDE function** to prevent zero-division errors.
  - **Data validation techniques** to ensure data accuracy.

Date and Time Analysis
  - Creating a **date table** using M language.

Power BI Services
  - **Publishing reports** to Power BI services.
  - Setting up a **personal gateway** for auto-refreshing data.
  - Creating and managing **Power BI Apps**.

  Collaboration and Sharing
  - Collaborating using **workspaces**.
  - Managing **access permissions** in Power BI services.


Here’s a structured approach to work on this project for **AltiQ Hardware**, focusing on the data, dashboard objectives, and analysis techniques:

---

### **Project Objective**
The primary goal is to use Power BI to analyze AltiQ Hardware’s sales, forecasts, and cost metrics, enabling stakeholders to make **data-driven decisions**. The dashboard should help the company:
- Recover from the unforeseen losses in the American market.
- Compete effectively by matching their competitors' analytics capabilities.
- Provide actionable insights into sales, customer preferences, and operational efficiency.

---

### **Kickoff Questions**
Before starting the project, ask the following questions to ensure clarity:  
1. **Objective and Success Metrics**:
   - What is the primary goal of the dashboard (e.g., revenue improvement, cost reduction, market analysis)?
   - How will the success of this dashboard be measured?  

2. **Stakeholder Insights**:
   - What are the key concerns and hopes of stakeholders?
   - Who are the end-users, and what will they use the dashboard for?

3. **Project Logistics**:
   - What is the timeline and key milestones?
   - Are there any required previews or feedback sessions before the final release?

4. **Design and Functionality**:
   - Do stakeholders have preferences regarding dashboard layout, visuals, or color schemes?
   - What are the most critical KPIs to be featured?

5. **Data and Resources**:
   - What data is available and its current state (e.g., completeness, accuracy)?
   - Are there any additional data points or inputs required for effective analysis?

---

### **Data Understanding**
#### **Datasets Overview**:
- **Dimension Tables** (Static Data):
  - `dim_customer`: Market, customer details, and sales platforms.
  - `dim_market`: Market hierarchies (regions, sub-zones).
  - `dim_product`: Product categories and variants.

- **Fact Tables** (Transaction Data):
  - `fact_forecast_monthly`: Monthly forecasts for customer needs, helping with cost reduction and customer satisfaction.
  - `fact_sales_monthly`: Monthly actual sales, similar structure to forecast data.

- **Cost and Pricing Data**:
  - `freight_cost`: Travel costs by market and fiscal year.
  - `gross_price`: Product-level gross prices.
  - `manufacturing_cost`: Costs at the product and year level.
  - `pre_invoice_deductions`: Customer-specific deductions before invoicing.
  - `post_invoice_deductions`: Other post-invoice deductions.

---

### **Steps to Develop the Power BI Dashboard**

#### **1. Data Preparation**
- Import data into Power BI from multiple sources.
- Clean and transform data in **Power Query**:
  - Ensure consistency in date formats and column names.
  - Remove duplicates and handle missing data.
- Create relationships between fact and dimension tables in the **data model**.

#### **2. Key Metrics and Calculations**
- Use **calculated columns** and **measures** for:
  - Sales vs. Forecast Analysis:
    - Total Forecasted Quantity
    - Total Sold Quantity
    - Forecast Accuracy = `(Sold Quantity / Forecast Quantity) * 100`
  - Profitability:
    - Gross Profit = `Gross Price - (Manufacturing Cost + Freight Cost + Deductions)`
    - Profit Margin = `(Gross Profit / Gross Price) * 100`

#### **3. Dashboard Features**
- **KPIs**:
  - Revenue, forecast accuracy, regional sales trends.
- **Dynamic Visualizations**:
  - Use **bookmarks** and **buttons** for switching between views.
  - Add **dynamic titles** based on filters like region, product category.
- **Conditional Formatting**:
  - Highlight regions or products with declining sales.
- **Interactive Filters**:
  - Enable drill-through for regions, markets, and customers.

#### **4. Advanced Features**
- **Date Table**:
  - Create a date table using **M language** for time-based analysis.
- **Zero-Division Error Handling**:
  - Use the `DIVIDE` function for safe calculations.

#### **5. Deployment and Maintenance**
- Publish the dashboard to **Power BI Services**.
- Set up a **personal gateway** for automatic data refresh.
- Create a **Power BI App** to distribute the dashboard to stakeholders.
- Manage access permissions in the workspace for collaboration.

---

### **Deliverables**
1. **Power BI Dashboard**:
   - Sales and forecast trends with drill-down options.
   - Regional performance and profitability insights.
   - Interactive filters for products, regions, and sales channels.

2. **Documentation**:
   - Include a README file explaining the data sources, dashboard features, and KPIs.
   - Provide a data dictionary describing the columns in each table.

3. **Presentation**:
   - Highlight key insights, such as reasons for losses in the American market and strategies to improve.
   - Share visual examples (charts, KPIs) during stakeholder review meetings.


Importing data into PowerBi
As the database is MySQL in this project, we need to import the datasets from Mysql database to PowerBi by providing the Database access credential


## Data Modeling

### Importance of Data Modeling
- **Foundation of the Report**: Data modeling is crucial as it determines how visuals are structured and related. Poor data modeling leads to slow performance and inaccurate insights.
- **Impact**: Efficient data modeling ensures that visuals are fast and easy to navigate, while poor models lead to slow load times and difficult analysis.

### Data Modeling Method
- **Snowflake Schema**:
  - **Fact Tables**: 
    - `fact_sales_monthly`: Contains transactional sales data.
    - `fact_forecast_monthly`: Contains forecasted data for sales and demand.
  - **Dimension Tables**:
    - `dim_customer`: Describes customer data, with attributes like region and platform type.
    - `dim_product`: Describes product data, including categories and variants.
    - `dim_market`: Describes market data with geographical and regional information.
  - **Date Table**: A dedicated Date Table to ensure time-based analysis is clean and efficient.

### Best Practices
- Establish clear relationships (one-to-many) between fact and dimension tables.
- Use normalized tables to avoid redundant data.
- Ensure that the data's granularity (e.g., daily, monthly) is appropriate for the analysis.
- Create calculated columns and measures as needed to enhance the analysis.

---

## Dashboard Design

### Home View
- **Purpose**: The entry point to the dashboard, allowing users to easily navigate to the required views.
- **Elements**:
  - Navigation buttons for each view (e.g., Info, Finance, Sales, Marketing, etc.).
  - A clear layout for intuitive use.

### Views
1. **Info View**:
   - Provides an overview of the project, objectives, and methodology.
   - Includes basic project details and dataset explanations.

2. **Finance View**:
   - Key Performance Indicators (KPIs): Revenue, Profit Margin, Expenses.
   - Visuals: Bar charts for revenue breakdown, line charts for trends, KPI indicators.

3. **Sales View**:
   - KPIs: Sales Trends, Regional Sales, Forecast Accuracy.
   - Visuals: Sales maps, sales trend graphs, and comparison of forecast vs. actual sales.

4. **Marketing View**:
   - KPIs: Campaign Performance, ROI, Conversion Rates.
   - Visuals: Funnel charts for customer conversion, scatter plots for marketing spend vs. ROI.

5. **Supply Chain View**:
   - KPIs: Stock Levels, Freight Costs, Delivery Performance.
   - Visuals: Heatmaps, line charts for delivery performance, bar charts for freight costs.

6. **Executive View**:
   - Provides high-level KPIs and overall performance summaries.
   - Allows decision-makers to see key metrics at a glance.

7. **Products View**:
   - KPIs: Product Performance, Sales by Product Category.
   - Visuals: Pie charts for product sales distribution, bar charts for sales by category.

8. **Support View**:
   - Provides support for users of the dashboard with FAQs and contact details.

---

## Project Outcome

### Decision-Making Support
- The dashboard enables stakeholders to make informed, data-driven decisions across finance, sales, and operations.

### Answering Business Questions
- The dashboard helps answer critical **"why"** questions regarding business performance:
  - Why is a specific product underperforming?
  - Why are sales down in a particular region?

### Enhanced Transparency
- The dashboard enhances data transparency and provides easy access to the insights needed to drive business growth and improve operations.

### Actionable Insights
- With actionable insights at their fingertips, business users can make quick decisions, improving the company’s overall agility.


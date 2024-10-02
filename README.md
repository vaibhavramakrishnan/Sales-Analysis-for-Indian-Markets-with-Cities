## Sales Insights and Performance Dashboard for NVIDIA

Analysed over 150,000 sales transactions for NVIDIA, which is facing issues in terms of its sales. My work as a Data Analyst is to unlock insights that are not visible before the sales team for decision support & automate them to reduce the manual time spent in data gathering. This is done by creating an automated SQL and Tableau dashboard [here](https://public.tableau.com/app/profile/vaibhav.ramakrishnan/viz/SalesAnalysis-IndianMarketsCustomers/Dashboard1) that optimizes revenue tracking, product mix strategies, and regional performance insights helping in data-driven decision making.

<img width="1440" alt="Screenshot 2024-08-07 at 9 44 33 PM" src="https://github.com/user-attachments/assets/f0e4a499-998a-4691-9fb7-2bd416219cdd">

### North Star Metrics and Dimensions

1. **Total Revenue Numbers:** Overall revenue generated during the analysis period.
2. **Sales Quantity Numbers:** Total units sold.
3. **Year-over-Year (YOY) Growth:** Comparing sales performance with previous years.
4. **Revenue Breakdown:** Analysis by regions, products, and customer segments.
5. **Revenue Trends:** Insights into how revenue evolves over time.

### Stakeholders Involved

1. **Sales Director**
2. **Marketing Team**
3. **Customer Service Team**
4. **Data & Analytics Team**
5. **IT**

### Success Criteria

1. Dashboard uncovering sales order insights with the latest data available
2. Sales team able to make better decisions & prove cost savings of total spend
3. Sales Analysts stop data gathering manually in order to save business time and reinvest in value-added activity

### Summary of Insights

1. Projected to boost quarterly revenue by 8.5% - through enhanced market penetration, and streamlining decision-making for 38 key customers
 
### Data Analysis Using SQL

1. Show all customer records

    `SELECT * FROM customers;`

1. Show total number of customers

    `SELECT count(*) FROM customers;`

1. Show transactions for Chennai market (market code for chennai is Mark001

    `SELECT * FROM transactions where market_code='Mark001';`

1. Show distrinct product codes that were sold in chennai

    `SELECT distinct product_code FROM transactions where market_code='Mark001';`

1. Show transactions where currency is US dollars

    `SELECT * from transactions where currency="USD"`

1. Show transactions in 2020 join by date table

    `SELECT transactions.*, date.* FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020;`

1. Show total revenue in year 2020,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and transactions.currency="INR\r" or transactions.currency="USD\r";`
	
1. Show total revenue in year 2020, January Month,

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020 and and date.month_name="January" and (transactions.currency="INR\r" or transactions.currency="USD\r");`

1. Show total revenue in year 2020 in Chennai

    `SELECT SUM(transactions.sales_amount) FROM transactions INNER JOIN date ON transactions.order_date=date.date where date.year=2020
and transactions.market_code="Mark001";`

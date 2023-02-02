# Sales-Insights-Data-Analysis

## Problem Statement:
This case study is based on a computer hardware business which is facing challenges in dynamically changing market. Sales director decides to invest in data analysis project and he would like to build Tableau dashboard that can give him real time sales insights.
-	Top 5 customers by customers and sales quantity 
-	2 Weakest region where sales are declining – Revenue  breakdown by cities – so we add extra discount at that places
-	Aggregate revenue in last 365 days - Revenue  breakdown by month and year 
-	Top 5 product by revenue number

## Aims grid
The Aim's Grid is a central tool for planning any venture and a must-have for project leaders. This tool helps you collect the most important information about your project on one simple page, laying the foundation for a successful implementation.

### 1. PURPOSE
To unlock sales insights that are not visible before for sales team for decision support & automate them to reduced manual time spent in data gathering.

### 2. STAKEHOLDERS/Clients
•	Sales Director
•	Marketing Team
•	Customer Service Team
•	Data & Analytics Team
•	IT

### 3. END RESULT
An automated dashboard is providing quick & latest sales insights in order to support data driven decision making. 

### 4. SUCCESS CRITERIA
•	Dashboard(s) uncovering sales order insights with latest data available
•	Sales team able to take better decisions & prove 10% cost savings of total spend
•	Sales Analysts stop data gathering manually in order to save 20% of their business time and reinvest it value added activity



## Data Exploration in SQL

•	Top 5 customers by customers and sales quantity  
SELECT c.custmer_name,SUM(t.sales_qty) as Total_purchased FROM transactions t JOIN customers c ON c.customer_code=t.customer_code GROUP BY t.customer_code ORDER BY Total_purchased DESC LIMIT 5

•	2 Weakest region where sales are declining – Revenue  breakdown by cities
UPDATE transactions  SET sales_amount=sales_amount*80.20   WHERE currency LIKE "USD"
UPDATE transactions SET currency="INR" WHERE currency="USD" ;
SELECT m.markets_name,SUM(t.sales_amount) AS revenue FROM transactions t JOIN markets m ON m.markets_code=t.market_code  GROUP BY t.market_code ORDER BY revenue LIMIT 2;


•	Aggregate revenue in last 365 days - Revenue  breakdown by month and year 
SELECT YEAR(order_date),MONTHNAME(order_date),SUM(sales_amount) FROM transactions GROUP BY YEAR(order_date),MONTHNAME(order_date) ORDER BY YEAR(order_date),MONTH(order_date); 

•	Top 5 product by revenue number
SELECT product_code,SUM(sales_amount) AS Revenue FROM transactions GROUP BY product_code ORDER BY Revenue DESC LIMIT 5





## `Dashboard 1`



![First Dashboard](https://user-images.githubusercontent.com/85899270/216389249-006d3f31-6b3d-43c2-927e-3bdcd9878f99.png)

 
## Feedback From Stakeholders




## `Revised Dashboard` 

![Revised-Dashboard](https://user-images.githubusercontent.com/85899270/216389293-f24c46eb-6bf4-4e26-9053-3de3a4ca96cd.png)

 


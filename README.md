# data-analytics-portfolio
Portfolio of data analytics projects covering sales analysis, customer segmentation, discount impact, and SQL-based reporting. Built with SQL, Python, Excel, and Power BI to showcase analytical, visualization, and problem-solving skills for business decision-making.
# 📊 Data Analytics Portfolio — Theresa Agu

A portfolio of data analytics projects covering **sales analysis, customer segmentation, discount impact, shipping analysis, geography insights, and SQL-based reporting**.  
Built with **SQL, Python, Excel, and Power BI** to showcase analytical, visualization, and problem-solving skills for business decision-making.

---

## 🧰 Skills & Tools
**SQL • Power BI • Tableau • Excel • Python**  
Data cleaning, joins/CTEs/window functions, DAX/Measures, KPI design, dashboarding, EDA, data storytelling.

---

## 📄 Resume
[THERESA AGU CV.docx](https://github.com/user-attachments/files/21860324/THERESA.AGU.CV.docx)

---

## 📚 Projects

### 1) Globalstore Sales Performance Dashboard
**Objective:** End-to-end analysis of sales, profit, discount, and segments.  
**Highlights:**
- Total Sales **£12.64M**, Profit **£1.47M**, Avg Margin **11.61%**
- Consumer segment leads; Phones, Copiers, Chairs top sub-categories  
**Tools:** Power BI, Excel
  
<img width="500" height="281" alt="overview png" src="https://github.com/user-attachments/assets/3aaca3f3-50ac-4081-bcea-773c8b8d8519" />

---

### 2) Geographical Sales & Profitability
**Objective:** Identify top cities/countries/regions by sales & profit.  
**Highlights:** NYC leads sales (~£0.26M); USA most profitable (~£0.29M).  
**Tools:** Power BI  

<img width="497" height="281" alt="geo png" src="https://github.com/user-attachments/assets/2ae0a576-024a-445d-b659-ca0b5989c192" />

---

### 3) Order Priority → Delivery & Profit
**Objective:** Understand how priority impacts profit and delivery time.  
**Highlights:** Medium priority contributes most profit (~£0.86M); Critical orders deliver fastest (~21 days).  
**Tools:** Power BI  

<img width="498" height="273" alt="orderpriority png" src="https://github.com/user-attachments/assets/99e8ab31-fad6-4589-82eb-be3b0fe5b222" />

---

### 4) Ship Mode Usage & Profitability
**Objective:** Compare margins and usage across shipping modes.  
**Highlights:** Margins ~11% across modes; **Standard Class = 60%** of orders.  
**Tools:** Power BI  


<img width="503" height="284" alt="shipmode png" src="https://github.com/user-attachments/assets/b710d8f5-a7cb-4517-97f4-5fd996e04670" />

---

### 5) Segment & Product Profitability Insights
**Objective:** Profit by customer segment and product sub-category.  
**Highlights:** Consumer profit ~£0.75M; Accessories & Copiers ≈ **17%** margins; Tech & Office Supplies outperform Furniture.  
**Tools:** Power BI, Excel  


<img width="504" height="285" alt="profit png" src="https://github.com/user-attachments/assets/55820a89-fb16-48fc-a14e-f25c2ee86f40" />

---

### 6) Monthly & Quarterly Sales Patterns (2011–2014)
**Objective:** Seasonality & growth trends across months/quarters.  
**Highlights:** Peak in **Q4 2014 (~£1.3M)**; November strongest month (~£0.51M).  
**Tools:** Power BI  

<img width="507" height="285" alt="salespattern png" src="https://github.com/user-attachments/assets/48430ccc-de8e-4ec6-90a3-fec7f85a0d5b" />

---

### 7) Discount Impact on Sales & Profitability
**Objective:** Quantify effect of discounts on profit.  
**Highlights:** Profit falls sharply beyond ~40% discount; Furniture averages the highest discount (~16.8%).  
**Tools:** Power BI  

<img width="506" height="276" alt="discount png" src="https://github.com/user-attachments/assets/0b408faf-ac90-4303-ad95-fd589d011914" />

---

### 8) SQL Project — Customer & Sales Order Analysis
**Objective:** Answer core business questions from a relational sales DB (`customers`, `agents`, `orders`).  
**Skills:** Joins, GROUP BY, aggregates, filters, CTEs/window functions (where applicable).

**Example queries:**
```sql
-- Agents and phone numbers
SELECT agent_name, phone_number FROM agents;

-- Highest purchase per customer
SELECT cust_code, MAX(order_amount) AS highest_purchase_amount
FROM orders
GROUP BY cust_code;

-- Customers and their agents
SELECT c.cust_name, a.agent_name
FROM customer c
JOIN agents a ON c.agent_code = a.agent_code;
[sql queries.sql](https://github.com/user-attachments/files/21860454/sql.queries.sql)
---1. Write a query to display all the agents name with their phone number from agents table.
select agent_name, phone_number
from agents

---2. Write a query to display the names of all the customers with working area is Leeds from customer table.
select * from customer
where working_area = 'leeds'

---3. Write a query to display the order number and order amount with order description is shoes from orders table.
select order_num, order_amount, order_description
from orders
where order_description = 'shoe' 

---4. Write a query to display the agent code, order amount and order description where order amount= 3000 and order description is clothes
select agent_code, order_amount, order_description
from orders
where order_amount = '3000' and order_description = 'clothes'

---5. Write a query to display all the details from the table order where the order amount is more than 2000.
select * from orders
where order_amount > '2000'

---6. Write a query to display customer name and customer phone number that have alphabet �e� in their name.
select cust_name, phone_number
from customer
where cust_name like '%e%'

---7. Write a query to display all the details from orders table with minimum order amount.
select * from orders
select min(order_amount) as minimum_order_amount from orders

---8. Write a query to display the total order amount from orders table.
select sum(order_amount) as total_order_amount from orders

---9. Write a query to find the number of agents currently listing for all of their customers from orders table.
select count(distinct agent_code) as agents_currently_listing from orders

---10. Write a query to find the highest purchase amount ordered by the each customer code and highest order amount.
select cust_code,max(order_amount) as highest_purchase_amount
from orders
group by cust_code

---highest order amount
SELECT MAX(order_amount) AS highest_order_amount
FROM orders

---11. Write a query to find the highest order amount on a date '2022-07-13' with agent code.
SELECT agent_code, order_amount
FROM orders
WHERE order_date = '2022-07-13'
  

---12. Write a query to find the name and customer city of those customers and agents who work in the same city.

SELECT c.cust_name, c.cust_city, a.agent_name, a.working_area
FROM customer c, agents a
WHERE c.working_area = a.working_area
  AND c.cust_city = a.working_area

  ---13. Write a query to find the name of all the customer names along with the agent names who works for them.
  SELECT c.cust_name, a.agent_name
FROM customer c
JOIN agents a
  ON c.agent_code = a.agent_code

  ---14. Write a query to display all those orders by the customers not located in the same cities where their agents working area.
  SELECT o.order_num, o.order_amount, o.order_date, c.cust_name, c.cust_city, a.agent_name, a.working_area
FROM orders o
JOIN customer c ON o.cust_code = c.cust_code
JOIN agents a ON o.agent_code = a.agent_code
WHERE c.cust_city != a.working_area

---15. Write a query to display all the orders issued by the agent 'Rickey' from the orders table.
SELECT o.order_num, o.order_amount, o.order_date, o.order_description
FROM orders o
JOIN agents a ON o.agent_code = a.agent_code
WHERE a.agent_name = 'Rickey'






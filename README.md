# Power-BI-Credit-Card-Analytics
Power BI Credit Card Analytics Dashboard Project

**PROJECT OBJECTIVE:** The objective of this project is to design and develop two interactive Power BI dashboards using the provided datasets to deliver actionable insights into Credit Card Customers and Credit Card Transactions. The dashboards are built around key performance metrics and enable analysis filtered by gender (Male/Female), Age Group and Income Group, supporting data-driven decision-making through clear and meaningful visualizations.

**FILES:** Credit Card Report Dashboard.pbix

**TOOLS USED:**
- Power BI
- Power Query
- DAX
- Microsoft Excel

## Dashboards

**DASHBOARD 1 – CREDIT CARD CUSTOMER REPORT:**

A. Filters Created(Using DAX Formula): 
	
	a. Income Group Filter: Allow filtering by income levels (Low, Medium, High). Created Column using DAX formula. Formula Used: Income_Group = SWITCH(TRUE(),
        customer[Income]<= 35000, "Low Income",
        customer[Income]< 70000, "Medium Income",
        customer[Income]>= 70000, "High Income")
        
	b. Age Group Filter: Filter customers based on age ranges (e.g., 18-25, 26-35, etc.). Created a column using DAX Formula. 
        Formula Used: Age_Group = SWITCH(TRUE(),
        customer[Customer_Age]>18 && customer[Customer_Age]<=25, "18-25",
        customer[Customer_Age]>25 && customer[Customer_Age]<=35, "26-35",
        customer[Customer_Age]>35 && customer[Customer_Age]<=45, "36-45",
        customer[Customer_Age]>45 && customer[Customer_Age]<=55, "46-55",
        customer[Customer_Age]>55 && customer[Customer_Age]<=65, "56-65",
        customer[Customer_Age]>65, "65+")
        
	c. Gender Filter: Provide an option to filter the entire dashboard by Male and Female.
        
**DASHBOARD 2 – CREDIT CARD TRANSACTION REPORT:**

A. Filters Created: 

a. Spending Category Filter: Filter by different Spending Categories.
b. Transaction Date Filter: Allow filtering by Week.
c. Gender Filter: Filter transactions by Male and Female.

**DAX FORMULA USED:**

1. To calculate Current Week Revenue: Current_Week_Rev= CALCULATE(SUM(CreditCard[Revenue]), FILTER(ALL(CreditCard), CreditCard[Week_Num]= MAX(CreditCard[Week_Num])))

2. To calculate Previous Weeks Revenue to create KPI Chart: Previous_week_Revenue = CALCULATE(SUM(CreditCard[Revenue]), DATEADD(CreditCard[Week_Start_Date], -7, DAY))

3. To calculate the Revenue: Revenue = CreditCard[Annual_Fees]+ CreditCard[Interest_Earned]+ CreditCard[Total_Trans_Amt]

**KEY INSIGHTS**

- Customers with a Graduate-level education contribute the highest revenue, with males generating slightly more revenue than females in this segment.
- Married Customers contribute the highest revenue, with Females generating slightly more revenue than Males in this segment.
- Bills and Entertainment are the highest spending categories
- Male customers contribute more to total transaction amount and Revenue.
- Some weeks show higher transaction activity, indicating seasonal trends.
- 46-55 Age group customers contribute most of the revenue.

**CONCLUSION:**
- This project demonstrates the ability to convert raw transaction data into clear, actionable business insights through Power BI.
- It highlights proficiency in data modelling, DAX calculations, and interactive dashboard design, analysis that supports informed decision-making.

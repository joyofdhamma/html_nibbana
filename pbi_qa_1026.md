```md
# Power BI Objective Questions

---

**Q1.** You preview an Excel file in Power Query Editor. The data is a matrix with years on columns, months on rows, and sales amount in the values. You need to shape it into a three-column table. What should you do?

- A. Pivot
- B. Transpose
- C. Unpivot
- D. Use First Row as Headers

**Answer: C. Unpivot**

---

**Q2.** You import an Excel file with one worksheet. The column names start on row 5. Column A has occasional blank values. You need to remove the blank rows at the top and use row 5 as headers. What should you do first?

- A. Remove empty values from the first column.
- B. Remove the top 4 rows.
- C. Use the current headers as the first row.
- D. Use the first row as headers.

**Answer: B. Remove the top 4 rows.**

---

**Q3.** An Excel file has two columns: categories and subcategories. You need a table with a separate column for each category, showing the count of subcategories. What transform should you use?

- A. Pivot
- B. Promote headers
- C. Transpose
- D. Unpivot

**Answer: A. Pivot**

---

**Q4.** A table has the columns LocationName, LocationID, Temperature, and DateTime. You need to build a star schema. Which table should get the LocationName field?

- A. Date Dimension
- B. Location Dimension
- C. Location Fact
- D. Temperature Measurements Fact

**Answer: B. Location Dimension**

---

**Q5.** A table has the columns ProductName, ProductID, SalesDate, and SalesAmount. You need to build a star schema. Which table should get the SalesAmount field?

- A. Product Dimension
- B. Product Fact
- C. Sales Dimension
- D. Sales Fact

**Answer: D. Sales Fact**

---

**Q6.** DimCustomer has one row per customer. FactOrder has one row per order. You need a relationship from DimCustomer (1-side) to FactOrder (many-side). Which cardinality should you choose?

- A. many-to-many
- B. many-to-one
- C. one-to-many
- D. one-to-one

**Answer: C. one-to-many**

---

**Q7.** FactInventory has one row per product per weekday. Balances are not recorded on weekends. DimDate is the date table. You need a measure showing the last available inventory balance for the selected period. Which DAX function should you use?

- A. EOMONTH
- B. FIRSTNONBLANK
- C. LASTNONBLANK
- D. NETWORKDAYS

**Answer: C. LASTNONBLANK**

---

**Q8.** A model has a Sales table with an OrderDate column. You need to show year-to-date (YTD) sales. The calculation must not be affected by filters on OrderDate. What should you do?

- A. Create a measure using SAMEPERIODLASTYEAR wrapped in CALCULATE with REMOVEFILTERS(Sales[OrderDate]). Add it to a card visual.
- B. Create a measure using SAMEPERIODLASTYEAR wrapped in CALCULATE with REMOVEFILTERS(Sales[OrderDate]). Add it to a KPI visual.
- C. Create the measure `YTD Sales (Ignore OrderDate) = CALCULATE(TOTALYTD([Sales Amount], Sales[OrderDate]), REMOVEFILTERS(Sales[OrderDate]))`. Add it to a card visual.
- D. Create the measure `YTD Sales (Ignore OrderDate) = CALCULATE(TOTALYTD([Sales Amount], Sales[OrderDate]), REMOVEFILTERS(Sales[OrderDate]))`. Add it to a KPI visual.

**Answer: C**

---

**Q9.** A model has a Sales table with a Date column. You create a YoY Sales Growth % measure using DATEADD('Sales'[Date], -1, YEAR). You need to configure the model so the calculation works. The model must stay small. What should you do?

- A. Add a date table with every day between 1/1/2020 and 12/31/2021. Create a relationship to the Sales table.
- B. Add the Date column from the Sales table to another table in the model.
- C. Create a new table with the Date column from Sales. Create a relationship to Sales on the Date column.
- D. Create a new table with the Date column from Sales. Create a relationship to Sales on the Date column. Set Mark as date table on the new table's Date column.

**Answer: D**

---

**Q10.** A model has Sales, Date, and Product tables. Sales has many-to-one relationships to Date and Product. Sales has a Total Sales Amount column. You need a Total Sales measure to aggregate by product or by date. What should you use?

- A. `Total Sales = ALL('Sales'[Total Sales Amount])`
- B. `Total Sales = CALCULATE([Total Sales])`
- C. `Total Sales = MAX('Sales'[Total Sales Amount])`
- D. `Total Sales = SUM('Sales'[Total Sales Amount])`

**Answer: D. `Total Sales = SUM('Sales'[Total Sales Amount])`**

---

**Q11.** Table1 has the columns Sales Date, Product ID, Quantity, Item Price, and Region. You need a measure named Avg Price - All Regions that averages item price across all regions. Which expression should you use?

- A. `CALCULATE( AVERAGE( Table1[Item Price] ), REMOVEFILTERS( Table1[Region] ) )`
- B. `CALCULATETABLE( AVERAGEX( Table1[Item Price] ), REMOVEFILTERS( Table1[Region] ) )`
- C. `CALCULATE( MEDIAN( Table1[Item Price] ), ALL( Table1[Region] ) )`
- D. `SUMMARIZE( Table1[Item Price] )`

**Answer: A**

---

**Q12.** DimDate is the date table. FactInventory is a snapshot table with one row per product per date. You need a Stock on Hand measure that returns the items in inventory on the last day of the selected period. It must work for a day, week, month, or year. Which formula should you use?

- A. `CALCULATE( SUM(FactInventory[UnitsBalance]), LASTDATE(DimDate[Date]) )`
- B. `CALCULATE( SUM(FactInventory[UnitsBalance]), LASTNONBLANK(DimDate[Date], CALCULATE(SUM(FactInventory[UnitsBalance]))) )`
- C. `CALCULATE( SUM(FactInventory[UnitsBalance]), FIRSTDATE(DimDate[Date]) )`
- D. `CALCULATE( SUM(FactInventory[UnitsBalance]), MAX(DimDate[Date]) )`

**Answer: B**

---

**Q13.** A Person table has a whole number column named Age. You need a DAX measure that finds the middle value of the Age values. What formula should you use?

- A. `AVERAGE('Person'[Age])`
- B. `MEDIAN('Person'[Age])`
- C. `RANK.EQ('Person'[Age], 'Person'[Age])`
- D. `STDEV.P('Person'[Age])`

**Answer: B. `MEDIAN('Person'[Age])`**

---

**Q14.** Performance analyzer shows high duration values for the Visual display category. What is a possible cause?

- A. misconfigured relationships
- B. too many columns in the underlying tables
- C. too many fields used in visuals
- D. unoptimized measures

**Answer: C. too many fields used in visuals**

---

**Q15.** A model has Sales and DimCustomer tables. LoyaltyCardNumber in DimCustomer is unused. EmailAddress is mostly blank and not needed. You need to optimize model performance. What should you do?

- A. Change the data type of EmailAddress to Text (string).
- B. Create an index on CustomerID in DimCustomer.
- C. Hide the LoyaltyCardNumber and EmailAddress columns.
- D. Remove the LoyaltyCardNumber and EmailAddress columns from the model.

**Answer: D**

---

**Q16.** A model holds five years of sales. It is 950 MB and the Sales table has five million rows. You need to minimize model size and still analyze:
- Current and previous year sales for all active products
- Current year sales by product category

What should you do?

- A. Remove the Product Status column.
- B. Remove the rows for inactive products.
- C. Remove the rows for sales that occurred more than two years earlier.
- D. Remove the Sale Date column.

**Answer: C**

---

**Q17.** A matrix visual shows profit for each quarter. You need to compare each quarter's profit with the previous quarter. Which DAX visual calculation should you use?

- A. `ProfitIncrease = MOVINGAVERAGE([Profit], 2)`
- B. `ProfitIncrease = [Profit] – NEXT([Profit])`
- C. `ProfitIncrease = [Profit] – PREVIOUS([Profit])`
- D. `ProfitIncrease = RUNNINGSUM([Profit], 2)`

**Answer: C**

---

**Q18.** A table visual displays units sold. You need a visual calculation showing the cumulative total for each row. Which template should you use?

- A. Moving average
- B. Percent of parent
- C. Running sum
- D. Versus last

**Answer: C. Running sum**

---

**Q19.** A report has a bar chart and a pie chart with default interactions. You want the pie chart to show only data related to the selected bar. You enable Edit Interactions. What should you do next?

- A. Select the pie chart and set the bar chart interaction to Filter.
- B. Select the pie chart and set the bar chart interaction to None.
- C. Select the bar chart and set the pie chart interaction to Filter.
- D. Select the bar chart and set the pie chart interaction to None.

**Answer: C**

---

**Q20.** A report has two pages. The first has a clustered bar chart. You plan to use the second page as a tooltip report. What should be done on the second page?

- A. The Allow Q&A setting must be enabled.
- B. The Allow use as tooltip setting must be enabled.
- C. Add employee count to the Tooltip field well.
- D. The Page view must be set to Actual size.

**Answer: B**

---

**Q21.** A workspace has two semantic models and five reports. You need to give all department users read access to one semantic model and three reports. Access must be removed automatically when users leave the department. Which two actions should you perform? (Select two.)

- A. Add the security group to the Viewer role on the workspace.
- B. Grant app access to the security group and publish the app.
- C. Set Include in App to Yes for all semantic models and reports.
- D. Set Include in App to Yes for the one semantic model and the three reports.
- E. Share the one semantic model and the three reports with each user.

**Answer: B and D**

---

**Q22.** Workspace1 holds a semantic model used by 10 reports. Only the development team uses Workspace1. You need to stop users from accessing the model directly from Workspace1, while still letting users collaborate on reports that use the same model. Minimize admin effort. What should you do?

- A. Assign Power BI Pro licenses to the users.
- B. Create a copy of the dataset in a new workspace.
- C. Create a new report in a new workspace that uses a live connection to the semantic model in Workspace1.
- D. Publish the reports to a new workspace.

**Answer: C**

---

**Q23.** Model1 has the tables Sales, Date, Product, and Employee. You need an RLS role where employees see only their own sales. The filter must match the user to their email address. Which table filter expression should you use?

- A. `Employee[EmailAddress] = USERCULTURE()`
- B. `Employee[EmailAddress] = USERNAME()`
- C. `Employee[EmailAddress] = USEROBJECTID()`
- D. `Employee[EmailAddress] = USERPRINCIPALNAME()`

**Answer: D. `Employee[EmailAddress] = USERPRINCIPALNAME()`**

---

**Q24.** A semantic model uses RLS. You need user1@contoso.com to see only data from the Los Angeles office. What should you do?

- A. Add user1@contoso.com to the Contributors group of the workspace that hosts the dataset.
- B. Add user1@contoso.com to the Contributors group of the workspace that hosts the dataset.
- C. Create a new role that shows only the Los Angeles office, then assign the role to user1@contoso.com.
- D. From the Power BI service, map user1@contoso.com to a username in the dataset.

**Answer: C**

---

**Q25.** Dataset1 has a Sales table with the columns Region, SalesAmount, and Date. You need all users to see only rows where Region is "North". What should you do?

- A. Apply a filter to the Region column in the report visual.
- B. Create a role in Power BI Desktop with the DAX filter `Sales[Region] = "North"`.
- C. Create a role that filters Sales[Region] using the USERNAME() function.
- D. Share the report only with users in the North region.

**Answer: B**
```

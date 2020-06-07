# MS Power BI and DAX formulas for Custom Time Intelligence 

<h2> Getting Started </h2>

Disclaimer: This code is designed for use with Power BI. DAX Formulas have been validated to work within Power BI and *should* work within MS Excel, provided the correct add-ons and extensions are installed. While the PowerQuery M Code is designed for use within Power BI, the code should also work within MS Excel.

<h3> Setting up the PowerQuery Date Tables </h3>

The PowerQuery Custom Date tables are found in the "M" source code folder. These queries are designed to pull dates from the current working dataset. The data source for the queries will have to be modified to work with your dataset. You will have to change the source data table and the date column within these queries to pull from your dataset. 

1. From your dataset, the queries will find the minimum date present within the data, that is the "Start Date." From there, it will calculate the First of the Year. That is, if your minimum date is 04/25/2020, the query will take this date and calculate the Start of the Year from it. The end result is 01/01/2020.

2. The "End Date" will find the maximum date within your dataset and calculate the year end date from that.

3. The Dates Table will create a contiguous date range from the Start Date to the End Date.

The Custom Date Table comes with: Year, Month, Quarter, Week of Year, Week of Month, Day, Day of Week, Day of Year, Name of Day, Name of Month, Start of Week, End of Week, Start of Month, End of Month, Start of Quarter, End of Quarter, Start of Year, and End of Year. There are three custom formulas for: Quarter and Year (formatted: \QQ yyyy), Named Year (formatted: \F\Y YYYY), and named quarter (formatted: \QQ). (formats contained a backslash (\\) denotes that the follow character is a *literal* character that appears. So, "\QQ" would appear as "Q1" or \F\Y yyyy" would appear as "FY 2020")

<h3> Marking the "Dates" Table as a Date Table within Power BI </h3>

Mark the "Dates" Table as a Date Table by navigate to the Modeling tab within Power BI. Click on the Mark As Date Table option within the Ribbon. Select the Date column and the prompt will say that the column has validated successfully. 

<h3> Creating the DAX formulas </h3>

The DAX formulas can be found within the DAX folder. Create a new custom measure within your data table, then copy and paste the formulas from the DAX folder into the formulas bar. You will need to update the Total Sales and Total Volume formulas to suit your the column names you are using within your dataset. 

<h3> Creating the active date relationship </h3>

You will need to create an active relationship between your "Dates" table and your data table. Click on the relationships view button to view the relationships window. Click the "Manage Relationships" button to open up the management window. Click "new" to create a new relationship. From the top drop down box, select the dates table, then click the Date column. In the bottom drop down, click your data table, then select your date column. Then click okay. An active relationship between the "Dates" table and your dataset has been created.

<h3> Thanks </h3>

Thanks to Enterprise DNA Team - https://enterprisedna.co

Thanks to Jeroen ter Heerdt - https://www.dutchdatadude.com/

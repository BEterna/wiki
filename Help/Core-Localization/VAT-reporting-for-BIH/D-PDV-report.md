#**Create D PDV report**

Additional reports which should be submitted with PDV report to BH tax authority by the 10th of next month for prior sales tax period.

##**Setup**
---
In order to be able to generate a D PDV form, the mandatory setup has to be completed.
Reporting codes
Reporting codes are used to direct amounts in appropriate columns of the report. List of all available reporting codes opens on the following path Modules - Tax - Setup - Sales tax - Sales tax reporting codes.
NOTE: Reporting codes used for the D PDV report should have the Bosnian report layout assigned.
Sales tax authorities setup
In order to enable Bosnian VAT reports layouts, this report needs to be defined on Tax authority.
Sales tax code setup
Each transaction that should be shown in the report should have an appropriate sales tax setup assigned. Setup that defines in which column of the report amounts will be shown are od the Report setup (for amounts with a positive sign) and Report setup – Credit note (for amounts with negative sign) tabs.
NOTE: Automatically reversed transactions will go in the same column as the original transaction. The mapping between reporting codes and D PDV form is in the File.
Generating report
3.	New VAT report is generated on the following path Modules - Open Tax – Declarations – Bosnia and Herzegovina – VAT – D PDV report.
4.	In order to run the report, the parameters should be set as follows:
•	Settlement period – choose the one related to the new VAT setup.
•	From date – enter the starting date of the VAT period.
•	Sales tax payment version – choose the Original option.
•	Print report – turn this parameter to Yes if D PDV the report should be printed.
4.	After click OK and D PDV form will be displayed

#**Create PDV report**

According to Article 39. of the Law on VAT every taxable entity is obligated to submit VAT report to the BIH tax authority by the 10th of next month for prior sales tax period. Sum and payment of VAT are calculated for overall receivable and payable transactions based on invoices in each tax period displayed in specific form.

##**Setup**
---
In order to be able to generate a PDV form, the mandatory setup has to be completed.

###**Reporting codes**
Reporting codes are used to direct amounts in appropriate columns of the report.
1. Go to Tax > Setup > Sales tax > Sales tax reporting codes.
2. Enter reporting codes for Bosnian layout. See the [list of available reporting codes](/Help/Core-Localization/VAT-reporting-for-BIH/KIF-and-KUF-report) for Bosnian layout.
NOTE: Reporting codes used for the PDV report should have the Bosnian report layout assigned.

###**Sales tax authorities setup**
In order to enable Bosnian VAT reports layouts, this report needs to be defined on Tax authority.

###**Sales tax code setup**
Each transaction that should be shown in the report should have an appropriate sales tax setup assigned. Setup that defines in which column of the report amounts will be shown are od the Report setup (for amounts with a positive sign) and Report setup – Credit note (for amounts with negative sign) tabs.
NOTE: Automatically reversed transactions will go in the same column as the original transaction. The mapping between reporting codes and POPDV form is in the File.
Generating report
1.	New VAT report is generated on the following path Modules - Tax - Declarations - Sales tax - Report sales tax for the settlement period.
2.	In order to run the report, the parameters should be set as follows:
•	Settlement period – choose the one related to the new VAT setup.
•	From date – enter the starting date of the VAT period.
•	Sales tax payment version – choose the Original option.
•	Print report – turn this parameter to Yes if PDV the report should be printed.
3.	After click OK and PDV form will be displayed

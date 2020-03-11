# Enhance the usage of Travel and Expenses

This chapter summarizes custom-developed features in the scope of the AdactaSuiteTravelAndExpenses AdSuite D365O extension packet that is described throughout the sections below.


## **Travel requisition enhancements**
---

This feature enhances standard D365O travel requisition functionality by adding the following functionalities:
   - Additional fields are added to travel requisition header: “From date and time”, “To date and time”, “By order of”, “Transport type” (Company-owned vehicle, Personal vehicle) and “Registration number”. “By order of” and “Registration number” are free text fields.
   - The estimated expense date of each travel requisition line must be within a period, entered on the travel requisition header (set with “From” and “To date and time” fields).
Using this feature, travel requisitions without lines can also be submitted to workflow and mapped to an expense report (if approved) if a setting “Enable submit to WF w/o lines” is enabled in Expense management parameters.
   - Two new travel requisition printouts are added with this feature:
     - Localized print (including details from each expense line) 
     - Localized print without lines (less detailed). 

Localized printouts become available only if the “Use localized reports” option is checked in Expense management parameters.


## **Expense report enhancements**
---

This feature enhances standard D365O Expense report functionality by adding the following functionalities.

### Fields on Expense report header

Additional fields are added to the Expense report header.

Open Expense report header:
   - “From date and time”, 
   - “To date and time”, 
   - “By order of”, 
   - “Transport type” (Company-owned vehicle, Personal vehicle) 
   - “Registration number”. “By order of” and “Registration number” are free text fields.

### Date Validation
   
Validation is executed upon expense report dates:
   - “Transaction date” entered for each expense line has to be within an entered period in expense report header localization fields From and To date and time. 

### Expense report print

Two new Expense report printouts are added with this feature:
   - Localized print (including details from each expense line) 
   - Localized print without lines (less detailed). 

Localized printouts become available only if the “Use localized reports” option is checked in Expense management parameters.

1. Open Expense management – Setup – General – Expense management parameters.
2. Localized reports are enabled in the Adacta section of expense management parameters. The same setting is used for the localized expense and travel requisition reports.

#### Localized print

1. Choose Print – Localized print on an expense report to generate the report. 

Note: if localized reports are not enabled in expense management parameters, the option “Localized print” is not available. 
 
2. The report shows the same types of information as the travel requisition localized print.
Amounts marked with a star (*) are included in the calculation “Remains for payment” – the amount that needs to be reimbursed to a worker.

### Map to travel requisition

This feature also enables Travel requisitions to be mapped to Expense reports. Upon mapping information from Travel requisition header and lines are transferred to the mapped Expense report. The feature works only if “Copy data from requisition” option is checked in Expense management parameters, while only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to an Expense report.

Upon mapping information from travel requisition header and lines are transferred to an expense report.

### Automatic Cash advance return line

If mapping Travel requisition with an applied cash advance (in status “Paid), upon transferring information from Travel requisition to mapped Expense report, additional expense line with expense type “Cash advance return” will be automatically created on an Expense report. The transaction amount and date for this newly generated line are transferred from cash advance (mapped to Travel requisition).

Additional setting in Expense management parameters: 
1. Open Expense management parameters - Adacta (expense).
2. Set field Apply cash advance return.

If the “Apply cash advance return” option is checked: mapping travel requisition (with applied cash advance in status “Paid”) to expense report will automatically create an additional line with expense type “Cash advance return”. Transaction amount and date are transferred from cash advance, connected with the mapped travel requisition.


## **Per Diem enhancements**
---

Additional features regarding per diems are added:
   - In terms of standard D365O functionality meal reduction for each meal in connection with per diem need to be entered as a percentage of the full per diem. This feature, however, enables that if field "Include percent" is marked, meal deductions will be calculated according to the value entered in field Meal percent. Otherwise, the deduction has to be entered as a percentage of full per-diem (e.g.  15% breakfast reduction for half per diem is calculated from the amount representing 75% of the full per diem).
   - Per diem transaction date on Expense reports can be defaulted from the last per diem day if the option is enabled in Expense management parameters.

### Per diem rate tiers: Include percent setup

1. Open Expense management – Setup – Calculations and codes – Per diems -> Per diem rate tiers.
2. Localization column “Include percent” is added to the form for per diem rate tiers setup. 
   - If field "Include percent" is marked, meal reductions will be calculated according to the value entered in field Meal percent, which represents the percentage of full daily allowance, defined in field Meals (e.g. 15% breakfast reduction for half perdiem is calculated from the amount representing 75% of the full perdiem).
   - If field “include percent” is not checked, it is necessary to adjust the percentages of meal reductions in relation to the full perdiem – reductions for meals have to be entered as percentages of full perdiem (e.g. reduction for breakfast for half perdiem represents 11.25% of the full perdiem).
 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**.
 
### 	Per diem transaction date on last day

#### Expense management parameters

1. Open Expense management/Setup/General/Expense management parameters/Adacta (expense).
2. Per diem transaction date can be set up on the last per diem day by enabling the feature in Expense management parameters. 
 
#### Transaction date on an expense report

1. Open Expense management – My expenses – Expense reports.
2. Upon saving the expense line “Per diem”, the Transaction date is automatically populated with the value from the field “Per diem to date”. 



## **Map cash advances to travel requisition**
---

This feature enables cash advances to be mapped to travel requisitions. Travel requisition can be chosen from the drop-down menu (field “Map to travel requisition”). “Amount” displays total travel requisition amount from the mapped requisition. Only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to a cash advance.

1. Added link to travel requisition. 
2. Travel requisition can be chosen in the field “Map to travel requisition”. 
3. “Amount” displays the total travel requisition amount from the chosen requisition. 

Only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to the cash advance.


## **Set up posting dates for group Expense report transactions posting**
---

This feature allows defining date for posting expenses in case of transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account (specified on payment method) is enabled. Using this functionality, expenses can be posted based on: (1) The earliest transaction date within the group; (2) The latest transaction date within the group; (3) Last date in a month of the transaction line with the latest date.

### Posting date of group transactions

1. Open Expense management – Setup – General – Expense management parameters.
2. The feature allows defining the date to post expenses on in case of enabled transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account specified in the payment method is enabled. 
 
Possible options are:
   - First of group: a transaction is posted on a date that is the earliest of all transaction dates.
   - Last of group: a transaction is posted on a date that is the latest of all transaction dates. 
   - Last in month: a transaction is posted on the last date of the month of the line with the latest date.
 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**.


## **Signatories on localized report printouts**
---

This feature enables signatories to be set in Expense management parameters. Chosen Signatories are displayed on both localized travel requisition and expense reports and are enabled only for the localized printouts. It is possible to set whether Left, Middle, or Right signatory will be displayed on printouts. It is also possible to enter the text in the adequate field for each of the enabled signatories, which will be displayed under the signature line (e.g. CEO).

### Setup

1. Signatories can be set in Expense management parameters. 
2. Chosen Signatories are displayed on localized travel requisition and expense reports. Signatories are enabled only for localized prints.
3. It is possible to set whether Left, Middle, or Right signatory will be displayed on the printout. Enter the text inadequate field for each of the enabled signatories which will be displayed under the signature line.
 


## **Mass delegation**
---

Standard D365O functionality for delegating is extended with the option to delegate a person for multiple Employees in one step. Mass delegation is enabled for Travel requisitions and Expense reports entry. As an addition to standard delegation option, (person by person) this feature enables a user to enter multiple delegates that belong to one department or Team. User, listed under Delegate, will be authorized to create Expense reports and Travel requisitions for all Employees that belong to Team/Department defined in field Team/Department.

1. Open Expense management/Setup/General/Delegates extended.
2. Mass delegation is enabled for Travel requisitions and Expense reports entry. As an addition to a standard delegation option (person by person), this feature enables a user to enter multiple delegates that belong to one department or Team. 
3. User, listed under Delegate, will be authorized to create Expense reports and Travel requisitions for all Employees that belong to Team/Department defined in field Team/Department. 
4. After setup is done, Update delegates function needs to be run. As a result of this function, lines will be generated in standard Delegate form. At the same time, the recurring batch job is generated, which will update lines in standard Delegate setup according to organizational changes in the related Department/Team. All lines that were generated from extended Delegate form, have a creation method set to Automatic. 
 
In case that the person that is delegated for other Employees also belongs to Team/Department that is delegated for, an additional line will be generated.


## **Delegates for Cash advances**
---

With Expense management enhancement package users can additionally generate Cash advances for other Employees if they are delegated for them (standard function “Delegates”). 

1. New function “Open other users cash advances” is added to the Cash advances page, which opens a list of delegated Employees. 
2. The user must select the employee for whom he wants to create a new Cash advance. After that the cash advance generation procedure is standard.


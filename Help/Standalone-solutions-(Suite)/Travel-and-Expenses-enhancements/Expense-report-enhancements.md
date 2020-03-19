## **Expense report enhancements**
---

This feature enhances standard D365O Expense report functionality by adding the following functionalities.

### **Fields on Expense report header**

Additional fields are added to the Expense report header.

Open Expense report header:
   - From date and time 
   - To date and time 
   - By order of 
   - Transport type (Company-owned vehicle, Personal vehicle) 
   - Registration number 
   - By order of 
   - Registration number 

### **Date Validation**
   
Validation is executed upon expense report dates: “Transaction date” entered for each expense line has to be within an entered period in expense report header localization fields From and To date and time.

Validation is optional and can be enabled/disabled in Expense management > Setup > General > Expense management parameters > Adacta (expense) > Ignore From-To date validation. 


|**Value**  | **Behavior** |
|--|--|
|Yes |Validation is not performed. There is no warning and the document can be submited to Workflow even if transaction is out of date range defined on the header of the document.  |
|No  |Validation is performed. Warning appears if transaction is out of date range defined on the header of the document and the document cannot be submited to Workflow. |



### **Expense report print**


1. Open Expense management – Setup – General – Expense management parameters.
2. Localized reports are enabled in the Adacta section of expense management parameters. The same setting is used for the localized expense and travel requisition reports.

#### Localized print

1. Choose Print – Localized print on an expense report to generate the report. 

Note: if localized reports are not enabled in expense management parameters, the option “Localized print” is not available. 
 
2. The report shows the same types of information as the travel requisition localized print.
Amounts marked with a star (*) are included in the calculation “Remains for payment” – the amount that needs to be reimbursed to a worker.

### **Map to travel requisition**

This feature also enables Travel requisitions to be mapped to Expense reports. Upon mapping information from Travel requisition header and lines are transferred to the mapped Expense report. The feature works only if “Copy data from requisition” option is checked in Expense management parameters, while only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to an Expense report.

Upon mapping information from travel requisition header and lines are transferred to an expense report.

### **Automatic Cash advance return line**

If mapping Travel requisition with an applied cash advance (in status “Paid), upon transferring information from Travel requisition to mapped Expense report, additional expense line with expense type “Cash advance return” will be automatically created on an Expense report. The transaction amount and date for this newly generated line are transferred from cash advance (mapped to Travel requisition).

Additional setting in Expense management parameters: 
1. Open Expense management parameters - Adacta (expense).
2. Set field Apply cash advance return.

If the “Apply cash advance return” option is checked: mapping travel requisition (with applied cash advance in status “Paid”) to expense report will automatically create an additional line with expense type “Cash advance return”. Transaction amount and date are transferred from cash advance, connected with the mapped travel requisition.


### **Set up posting dates for group Expense report transactions posting**

This feature allows defining date for posting expenses in case of transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account (specified on payment method) is enabled. Using this functionality, expenses can be posted based on: (1) The earliest transaction date within the group; (2) The latest transaction date within the group; (3) Last date in a month of the transaction line with the latest date.

#### Posting date of group transactions

1. Open Expense management – Setup – General – Expense management parameters.
2. The feature allows defining the date to post expenses on in case of enabled transaction grouping. Posting date setup is applicable only when a standard grouping of transactions based on the offset account specified in the payment method is enabled. 
 
Possible options are:


|**Value**  |**Description**  |
|--|--|
|First of group  |Transaction is posted on a date that is the earliest of all transaction dates.  |
|Last of group  | Transaction is posted on a date that is the latest of all transaction dates. |
|Last in month |Transaction is posted on the last date of the month of the line with the latest date. |

 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**.
## **Travel requisition enhancements**
---

This feature enhances standard D365O travel requisition functionality by adding the following functionalities:

### **Fields on Travel requisition header**
Additional fields are added to travel requisition header: 
   - From date and time 
   - To date and time 
   - By order of 
   - Transport type (Company-owned vehicle, Personal vehicle) 
   - Registration number 
   - By order of 
   - Registration number 

### **Date Validation**

The estimated expense date of each travel requisition line must be within a period, entered on the travel requisition header (set with “From” and “To date and time” fields). This feature can be enabled/disabled with parameter in Expense management parameters > Adacta (expense) > Ignore Form-To date validation. If set to No, dates from travel requisition lines will be validated against dates in the document header.   

### **Submit travel requisition without lines into Workflow**
Parameter for submission of Travel requisition is added to Expense management parameters > Adacta (expense) > Enable submit to WF w/o lines. If set to yes, travel requisition can be submitted to  Workflow without lines.


### **Travel requisition report print**
   - Two new travel requisition printouts are added with this feature:
     - Localized print (including details from each expense line) 
     - Localized print without lines (less detailed). 

Note: Localized printouts become available only if the “Use localized reports” option is checked in Expense management parameters.

### **Generate Expense report from Travel requisition**

It is possible to generate Expense report directly form approved Travel requisition. Function "Create expense report is added to Travel requisition list page. If approval status is different from Approved or Reconciliation status is set to Closed, function is disabled. 
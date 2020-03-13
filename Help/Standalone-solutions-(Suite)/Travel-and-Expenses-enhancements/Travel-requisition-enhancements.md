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

The estimated expense date of each travel requisition line must be within a period, entered on the travel requisition header (set with “From” and “To date and time” fields). Using this feature, travel requisitions without lines can also be submitted to workflow and mapped to an expense report (if approved) if a setting “Enable submit to WF w/o lines” is enabled in Expense management parameters.


### **Travel requisition report print**
   - Two new travel requisition printouts are added with this feature:
     - Localized print (including details from each expense line) 
     - Localized print without lines (less detailed). 

Note: Localized printouts become available only if the “Use localized reports” option is checked in Expense management parameters.
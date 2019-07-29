With Expense management enhancement package users can additionally generate Cash advances for other Employees if they are delegated for them (standard function “Delegates”). New function “Open other users cash advances” is added to Cash advances page, which opens list of delegated Employees. User must select the employee for whom he wants to create new Cash advance. After that the cash advance generation procedure is standard.

Specific custom developed features in scope of the AdactaSuiteTravelAndExpenses AdSuite D365O extension packet are described throughout the sections below.

-----

#Delegates for Cash advances

With Expense management enhancement package users can additionally generate Cash advances for other Employees if they are delegated for them (standard function “Delegates”). New function “Open other users cash advances” is added to Cash advances page, which opens list of delegated Employees. User must select the employee for whom he wants to create new Cash advance. After that the cash advance generation procedure is standard.

[Detailed documentation](http://axweb/D365O%20INIT%20Documents/D365O%20AdSuite_Expense%20management.docx?Web=1) (chapter 8)

-----

#Expense report enhancements

This feature enhances standard D365O Expense report functionality by adding the following functionalities:
-	Additional fields are added to Expense report header: “From date and time”, “To date and time”, “By order of”, “Transport type” (Company owned vehicle, Personal vehicle) and “Registration number”. “By order of” and “Registration number” are free text fields.
-	Validation is executed upon expense report dates – “Transaction date” entered for each expense line has to be within entered period in expense report header localization fields From and To date and time. 
-	Two new Expense report printouts are added with this feature - Localized print (including details from each expense line) and Localized print without lines (less detailed). Localized printouts become available only if “Use localized reports” option is checked in Expense management parameters.
-	This feature also enables Travel requisitions to be mapped to Expense reports. Upon mapping information from Travel requisition header and lines are transferred to the mapped Expense report. Feature works only if “Copy data from requisition” option is checked in Expense management parameters, while only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to Expense report.
-	If mapping Travel requisition with applied cash advance (in status “Paid), upon transferring information from Travel requisition to mapped Expense report, additional expense line with expense type “Cash advance return” will be automatically created on Expense report. Transaction amount and date for this newly generated line are transferred from cash advance (mapped to Travel requisition).

[Detailed documentation](http://axweb/D365O%20INIT%20Documents/D365O%20AdSuite_Expense%20management.docx?Web=1) (chapter 4)

-----

#Map cash advances to travel requisition

This feature enables cash advances to be mapped to travel requisitions. Travel requisition can be chosen from the drop down menu (field “Map to travel requisition”). “Amount” displays total travel requisition amount from the mapped requisition. Only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to cash advance.

[Detailed documentation](http://axweb/D365O%20INIT%20Documents/D365O%20AdSuite_Expense%20management.docx?Web=1) (chapter 3)

-----

#Mass delegation

Standard D365O functionality for delegating is extended with option to delegate a person for multiple Employees in one step. Mass delegation is enabled for Travel requisitions and Expense reports entry. As addition to standard delegation option, (person by person) this feature enables user to enter multiple delegates that belong to one department or Team. User, listed under Delegate, will be authorized to create Expense reports and Travel requisitions for all Employees that belong to Team/Department defined in field Team/Department.


[Detailed documentation](http://axweb/D365O%20INIT%20Documents/D365O%20AdSuite_Expense%20management.docx?Web=1) (chapter 7)

-----

#Per Diem enhancements

Additional features regarding per diems are added:

-	In terms of standard D365O functionality meal reduction for each meal in connection with per diem need to be entered as percentage of the full per diem. This feature, however enables that if field "Include percent" is marked, meal deductions will be calculated according to value entered in field Meal percent. Otherwise deduction has to be entered as percentage of full per-diem (e.g.  15% breakfast reduction for half per diem is calculated from the amount representing 75% of the full per diem).
-	Per diem transaction date on Expense reports can be defaulted from the last per diem day if option is enabled in Expense management parameters.

[Detailed documentation](http://axweb/D365O%20INIT%20Documents/D365O%20AdSuite_Expense%20management.docx?Web=1) (chapter 1)
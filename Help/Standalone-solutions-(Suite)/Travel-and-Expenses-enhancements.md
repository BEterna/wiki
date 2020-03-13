# Enhance the usage of Travel and Expenses

This chapter summarizes custom-developed features in the scope of the AdactaSuiteTravelAndExpenses AdSuite D365O extension packet that is described throughout the sections below.




## **Cash advance enhancements**
---

### **Map cash advances to Travel requisition**

This feature enables cash advances to be mapped to travel requisitions. Travel requisition can be chosen from the drop-down menu (field “Map to travel requisition”). “Amount” displays total travel requisition amount from the mapped requisition. Only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to a cash advance.

1. Added link to travel requisition. 
2. Travel requisition can be chosen in the field “Map to travel requisition”. 
3. “Amount” displays the total travel requisition amount from the chosen requisition. 

Only travel requisitions in Reconciliation status “Open” and Approval status “Approved” can be mapped to the cash advance.

## **Per Diem enhancements**
---

Additional features regarding per diems are added:

   - In terms of standard D365O functionality meal reduction for each meal in connection with per diem need to be entered as a percentage of the full per diem. This feature, however, enables that if field "Include percent" is marked, meal deductions will be calculated according to the value entered in field Meal percent. Otherwise, the deduction has to be entered as a percentage of full per-diem (e.g.  15% breakfast reduction for half per diem is calculated from the amount representing 75% of the full per diem).
   - Per diem transaction date on Expense reports can be defaulted from the last per diem day if the option is enabled in Expense management parameters.

### **Per diem rate tiers: Include percent setup**

1. Open Expense management – Setup – Calculations and codes – Per diems -> Per diem rate tiers.
2. Localization column “Include percent” is added to the form for per diem rate tiers setup. 

| **Value** | **Description** |
|--|--|
| field "Include percent" is marked |meal reductions will be calculated according to the value entered in field Meal percent, which represents the percentage of full daily allowance, defined in field Meals (e.g. 15% breakfast reduction for half perdiem is calculated from the amount representing 75% of the full perdiem).  |
| field “include percent” is not marked|it is necessary to adjust the percentages of meal reductions in relation to the full perdiem – reductions for meals have to be entered as percentages of full perdiem (e.g. reduction for breakfast for half perdiem represents 11.25% of the full perdiem).  |

 
 
Check **[Test Scenario](Travel-and-Expenses-Test-Scenario.zip)**.
 
### 	**Per diem transaction date on last day**

#### Expense management parameters

1. Open Expense management > Setup > General > Expense management parameters > Adacta (expense).
2. Per diem transaction date can be set up on the last per diem day by enabling the feature in Expense management parameters. 
 
#### Transaction date on an expense report

1. Open Expense management > My expenses > Expense reports.
2. Upon saving the expense line “Per diem”, the Transaction date is automatically populated with the value from the field “Per diem to date”. 




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


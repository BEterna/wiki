# Enhance the usage of Travel and Expenses

This chapter summarizes custom-developed features in the scope of the AdactaSuiteTravelAndExpenses AdSuite D365O extension packet that is described throughout the sections below.




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


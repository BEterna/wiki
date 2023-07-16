#Purpose 
---
Purpose of the Projects plan report is to provide consolidated data about project transactions. The report offers the overview of planned, realized, not activated realized and remaining amounts per investment project and project category. When a separate hierarchy is used for implementation projects, implementation project transaction amounts are showed on the investment projects based on the projects linking and projects category mapping setup.

#Setup 
---
Projects plan report shows the amounts based on three different setups previously described in this section: P[rojects linking](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/85/Enhancements-for-projects?anchor=projects-linking), [Project allocations](/Help/Standalone-solutions-\(Suite\)/Investment-management/Project-allocation) and [Project category mapping](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/85/Enhancements-for-projects?anchor=project-category-mapping). 

##Projects linking
When two separate project hierarchies are used for implementation and investment projects, implementation project transactions amounts are shown on the investment project based on the Projects linking. 

Rules for displaying implementation project transaction amounts on investment projects in the Not activated realized amount filed in Projects plan are the following:
- If there is only one linking between implementation and investment project, implementation project transaction amounts will be shown on that investment project as not activated realized amount.
- If implementation subproject does not have linking, linking of the parent implementation project is considered.
- If implementation project does not have configured linking, amounts are not added to any investment project and the following warning message is shown in Projects plan: _Link between investment project and implementation project "XY" does not exist._
- If implementation project has more than one linking within one investment project, amounts are added on the first mutual parent project of investment projects that are part of linking.
- Implementation project cannot be linked with different investment projects. In case that such linking is attempted, following error message appears: _Implementation project "XY" is already assigned to investment project "YX" (and not project allocation)"._

##Project allocations
Project allocations setup for Projects plan works in combination with Projects linking setup. Projects linking will not allow linking one implementation project with two investment projects that are part of different project allocations. In case that such linking is attempted, following error message appears: _Implementation project "XY" is already assigned to project allocation "YX"._

##Project category mapping
Implementation project transaction amounts are mapped to project categories based on the Project category mapping explained in [Project category mapping](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/85/Enhancements-for-projects?anchor=project-category-mapping). 

# Projects plan report 
---

To access Projects plan, navigate to _Project management and accounting > Projects > Projects plan_. Projects plan report calculation is started by clicking the button Update. Next, a new pop-up is displayed with the following fields:
- Category ID: select if the report should be updated only for a specific Project category 
- Project ID: select if the report should be updated only for a specific Project

If both fields are left blank, the report will be updated for all projects and project categories.

Records to include tab offers an additional possibility for filtering. Default filters are defined for Project type – Investment and Project subtype – Investment, meaning that only projects with the type and subtype Investment will be shown in the report. After clicking the button OK, the report is updated.

The report provides following information:

| Field |Description  |
|--|--|
| **Project ID** | project identification |
|  **Category** |  project category|
|**Planned amount**   |shows the forecasted amount per project and project category |
| **Realized amount**  | shows the amount of posted investment project transactions per project and project category. If implementation project transaction is activated to the investment project via Project activation proposal, its amount is also included in the Realized amount |
| **Not activated realized amount**  | shows the amount of posted implementation project transactions based on the Projects linking and Project category mapping setup. If an implementation transaction is partially activated to investment project, activated amount is included in Realized amount, while the remaining amount is shown in the Not activated realized amount |
|  **Remaining amount** |  = Planned amount – Realized amount – Not activated realized amount |


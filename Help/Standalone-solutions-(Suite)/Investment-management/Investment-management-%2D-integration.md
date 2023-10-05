Investment management package provides a set of industry specific functionalities meant for companies where assets, their construction and maintenance, present the backbone of their business. These functionalities are implemented as part of three modules in D365FO:
- Project management and accounting 
- Inventory management
- Fixed assets

Part of the Investment management package is an integration layer including:
- D365FO integration specific parameters (IM setup).
- Set of integration interfaces that a 3rd party system can use to access (create, read, update, delete) data related to the investment management process in D365FO.

# Integration specific parameters (IM Setup)
---
## Project structure types
In order to categorize different types of investment project a new information is introduced: Project structure type.
To define new project structure type:
1. Go to **Project management and accounting > Setup > Projects > Project structure types**
2. Define Name(must be unique) and Description

The project structure type can be defined for each project:
1. Go to **Project management and accounting > Project > tab General**: reference to Project structure types form

##IM Integration parameters 
1. Go to **Project management and accounting > Setup > Project management and accounting parameters**
2. Select **IM integration** tab
3. In the **General** fast tab the parameters define several project default values used when the project is created through the IM integration process. These parameters are:
   - Project structure type: definition of the default stage and subproject format for a specific project structure type. When a project is created through IM integration process these default values will be used for a specified project structure type.
   - Project contract: rules for automatic creation of project contracts when the project is created through IM integration process. For a selected combination of project group, customer account the rule is defined in the column Use project contract:
      - None (meaning no contract will be created and linked to the project).
      - New (meaning when the project is created a new project contract is also created for it).
      - Existing (meaning when the project is created, it is linked to an existing project contract) – if selected, a value in column Project contract ID must be specified. NOTE: This option includes an additional parameter "Do not create new funding source", meaning that the customer defined on a project will be also added as a founding source to the project contract when this check mark is not selected.
4. In the **Project forecasts** fast tab the parameters define how project forecasts are created through IM integration process(only expense forecasts are supported): 
      - Expense forecast category: defines the default expense project category used when expense project forecasts 
 are created through the IM integration process.
4. In the **Project requirements** fast tab the parameters define how project demands are created through IM integration process: 
      - Attachment type for URL: defines the attachment document type to be used for attachments on item requirements when item requirements are created through IM integration process.
      - Skip PR submit to workflow: defines if purchase requisitions for projects are or are not submitted to the workflow automatically through the IM integration process.
      - Item return transfer warehouse: defines the default terrain warehouse when returning items from project to inventory (see details under [Item returns](/Help/Investment-management/Item-returns/Item-returns).
4. In the **Project consumption** fast tab the parameters define how project consumption is created through IM integration process: 
      - Item journal: defines the Project item type of journal to be used for project item consumption.
      - Expense journal: defines the Project expense type of journal to be used for project expense consumption.
      - Hour journal: : defines the Project hour type of journal to be used for project hour consumption.
      - Maximum lines per journal: defines the maximum number of rows that will be processed within one recurrence of the consumption job.

##Project groups 
IM integration parameters that are defaulted from a project group are added to the project group form:
1. Go to **Project management and accounting > Setup > Posting > Project groups**.
2. Under **Investment management** fast tab the IM parameters are:
      - Project financial dimension: defines the name of the financial dimension that represents projects.
      - Default customer account: defines the customer account that will be defaulted when the project for the selected project group will be created through the IM integration process (this parameter does not apply when the project is created manually in D365FO)
      - Create project allocation: when set to "Yes" a new project allocation is created whenever a new project for the selected project group is created. The new project allocation is linked to the newly created project.
      - Project allocation applies to hierarchy: defines if the created project allocation applies to the project hierarchy or not.

# Integration interfaces 
---

##Data entities
With Investment management package, new data entities are available for integration purposes:
- Project structure type (ProjStructureTypeEntity_AdIMI)
- Projects entity (Projects_AdIMI)
- Project financing type (ProjectFinancingTypes_AdIMI)
- Projects linking (ProjImplInvLinkEntity_AdIM)
- Technical asset (TechnicalAssets_AdIMI)
- Technical asset categories (AssetCategories_AdIMI)
- Technical assets on projects (ProjectTechnicalAssets_AdIMI)
- Project expense consumption (ExpenseConsumption_AdIMI)
- Project hours consumption (ProjHourConsumptions_AdIMI)
- Project item consumption (ItemConsumptions_AdIMI)
- Project activation proposal (ProjActivationProposals_AdIM)
- Project item Requirement delivery (ProjItemRequirementDeliveries_AdIMI)

Updated data entities with Investment management package that include new fields (e.g. External ID of a record) are the following:
- Project expense forecasts (ExpenseConsumption_AdIMI)
- Project item requirements (ProjectSalesItemRequirements)

##Custom services
For implementing specific integration scenarios that cannot be covered by using Data entities in D365FO, there are custom services available to third party systems:
- Purchase requisition (insert of header and lines)
- Inventory state (state of current inventory)
- Asset values


Check [Postman collection examples](https://documenter.getpostman.com/view/11980146/2s946feDLt).
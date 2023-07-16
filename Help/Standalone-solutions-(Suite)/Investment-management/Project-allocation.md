# The Project allocation tracking dimension
---
Investment management package introduces an additional tracking dimension – Project allocation (PA). This dimension allows us to **track inventory that is required for a particular project** and cannot be used for other projects or needs. This is usually needed for items, which are not consumables. This way, inventory tracking is easier, and it allows us to track items even when they are located on project terrain and are not yet consumed for a project (i.e. built into an asset).

To start using the new tracking dimension, the license configuration key has to be enabled. This can only be turned on by an administrator of the system. To enable configuration key, navigate to _System administration > Setup > License configuration > section Trade_ and enable _Tracking dimension – Project allocation configuration key._

Once the configuration key is enabled, Project allocation will be available in _Product information management > Setup > Dimension and variant groups > Tracking dimension groups._ Set the check-marks in fields Active and Physical inventory in the Project allocation section of a selected tracking dimension group to make the Project allocation dimension required for an item that will be tracked with this group. Project allocation tracking dimension will be required for items in the same way as any other mandatory dimension throughout the system. 

With this tracking dimension enabled, users can review on-hand inventory status per project allocation, simply by displaying the Project allocation tracking dimension.

## Code list of project allocations

The code list of project allocations is available in _Inventory management > Setup > Inventory breakdown > Project allocations._

New project allocation values are created using the button New. Add **Name** and **Description** and establish a relation to a **Project** (select from the drop-down list). A project can only be assigned to project allocation once. The Project allocation field is a unique value and cannot be repeated.

If **Applies to hierarchy** field is marked, the relation of project allocation is valid for all sub-projects of the selected project, as well as for all implementation projects that are linked to investment projects through the Project linking setup. For more details about Project linking, please refer to the [Projects linking](/Help/Standalone-solutions-\(Suite\)/Investment-management/Enhancements-for-projects)?anchor=projects-linking) chapter. 

It is not allowed to relate a subproject to a project allocation if its parent project is already related and has a check-mark in the Applies to hierarchy field.

## Validation of project allocations
Validation of project and project allocation combination is executed for **purchasing and consumption** of items. If the combination of project and selected project allocation is not allowed, the system displays a warning that prevents the user from continuing with the invalid combination. 
 
Additional validation is executed, when PO line does not include Project ID, but it includes specific PA that is related to a project. This combination is allowed because when PO is created via Master planning (for an existing transfer order that was created for item requirement with different warehouses), such PO does not have information about Project ID. The user receives information about this case, stating that "Project allocation is selected but no project is specified". Users can then continue processing PO by either changing PA to a value that is not related to a project or keeping the selected PA.

The rules for **purchasing** (the same rules also apply when doing registration of items through the Registration form):
| **Item** |  **Project allocation used on purchase document**| **Project used on purchase document**  | **Is allowed** |
|--|--|--|--|
| PA tracking |  linked to a project|  related to this PA|Yes  |
| PA tracking | linked to a project | related to different PA | No |
|PA tracking  | linked to a project | has no PA relation  |  No|
|PA tracking*  | linked to a project |  /|  Yes|
|PA tracking  | not linked to any project | related to different PA |  No|
|PA tracking  |  not linked to any project| has no PA relation |  Yes|
|PA tracking  | not linked to any project |  /| Yes  |
|No PA tracking  | / | related to a PA |Yes |
|No PA tracking  |  /|no PA relation  |Yes |
|No PA tracking  | / |/  |Yes   |
*User receives an info log message as mentioned above.

The rules for item **consumption** on a project:
| **Item** |  **Project allocation used on project consumption document**| **Project used on project consumption document**  | **Is allowed** |
|--|--|--|--|
| PA tracking |  linked to project|  related to this PA|Yes  |
| PA tracking | linked to project | related to different PA | No |
|PA tracking  | linked to project | has no PA relation  |  No|
|PA tracking  | not linked to any project | related to different PA |  Yes|
|PA tracking  |  not linked to any project| has no PA relation |  Yes|
|PA tracking  | not linked to any project |  /| Yes  |
|No PA tracking  | / | related to a PA |Yes |
|No PA tracking  |  /| has no PA relation  |Yes |


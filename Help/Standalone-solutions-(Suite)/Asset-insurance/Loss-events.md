# Setup
---
Prior to creating a loss event, the setup described below is required.

## Case categories
Case categories for loss events are configured in the Organization administration module, **Organization administration > Setup > Cases > Case categories**. In the Case categories setup, a new case category with type Loss event is needed. Such case categories can be used on loss events. Each case category can be linked with case process. 

## Case processes

Case processes for loss events are configured in Organization administration module, **Organization administration > Setup > Cases > Case processes**. Case processes is standard D365FO functionality, which is used also for loss events. Case processes enable monitoring different stages throughout the loss event.

## Closure reasons

Closure reasons are listed in **Fixed assets > Setup > Insurance > Loss event**. Closure reason provides an additional information about closure of a loss event.

1. Go to **Fixed assets > Setup > Insurance > Loss event > Closure reasons**.
1. **Add code lists** for Closure reasons.

# Creating a loss event
---
To create a new loss event, navigate to **Fixed assets > Insurance > Loss events > All cases**. It is also possible to access only specific loss events from Fixed assets > Insurance > Loss events, such as My cases, Open cases, etc.
After opening All cases, the Grid view shows all created loss events. 

## New loss event pop-up

When clicking the **New** button, there is a possibility for creating a new **parent loss event (option Case)**, or **child/dependent loss event (option Dependent case)**. 

When selecting the Case button, a new blank pop-up is opened and basic information about loss event can be added. 

### **General** pane:

| Field             | Description                                                                                                                                                                                                 |
|-------------------|-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Name**          | Drop-down list of parties from Global address book (this value is populated automatically based on the Vendor from Insurance policy selected in the Loss event pane, but it can be added/changed manually.) |
| **Case category** | Drop-down list of Case categories with Category type Loss event only                                                                                                                                        |
| **Category type** | Filled in automatically based on Case category (Loss event)                                                                                                                                                 |
| **Case ID**       | Automatic number based on number sequence. The Number sequence is set in Organization administration > Organizations > Legal entities > Number sequence fast tab.                                           |
| **Status**        | Drop-down with options Open, In process, Closed and Canceled                                                                                                                                                |
| **Description**   | Manual entry of event description                                                                                                                                                                           |
| **Priority**      | Drop-down from table Priority (Sales and marketing > Setup > Leads > Priority)                                                                                                                              |
| **Parent case**   | Drop-down list of other loss events                                                                                                                                                                         |

### **Loss event** pane:

| Field                             | Description                                                                                                                                                  |
|-----------------------------------|--------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Insurance policy**              | Drop-down list of insurance policies                                                                                                                         |
| **Insurance coverage type**       | Drop-down list based on the selected insurance policy. Insurance coverage types added on the chosen insurance policy can be selected.                        |
| **Damage cause**                  | Drop-down list based on the selected insurance coverage type. Damage causes added to Insurance coverage type on the chosen insurance policy can be selected. |
| **Insurance type**                | Filled in automatically from the Insurance policy. If Insurance policy is not selected, this field is blank.                                                 |
| **Occurrence date of loss event** | Date showing when the loss event occurred                                                                                                                    |
| **Nature impact**                 | Yes/No checkmark filled in automatically based on the selected Damage cause. The value can be changed manually, if needed.                                   |
| **Cause of the loss event**       | Free text field to enter more details about loss event cause                                                                                                 |
| **Remediation method**            | Free text field to enter more details about remediation method                                                                                               |
| **Responsible for damage**        | Free text field to enter more details about responsible party for damage                                                                                     |
| **Aggrieved party**               | Free text field to enter more details about aggrieved party for damage                                                                                       |


### **Other** pane:

| Field                       | Description                                                                                                                                                                                                         |
|-----------------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Department**              | Drop-down list of Departments (Organization administration > Organizations > Operating units with filter Department in the Operating unit type field)                                                               |
| **Employee responsible**    | Drop-down list of employees (Human resources > Workers > Employees). This field is automatically filled in with the employee connected to the user, who is creating the loss event, but it can be changed manually. |
| **Service level agreement** | Drop-down list of service level agreements (Service management > Setup > Service agreements > Service level agreements)                                                                                             |
| **Case process**            | Drop-down list of case processes (Organization administration > Setup > Cases > Case processes)                                                                                                                     |

### **Case** pane:

| Field           | Description                                      |
|-----------------|--------------------------------------------------|
| **Description** | Free text field to enter more details, if needed |
| **Notes**       | Free text field to enter more details, if needed |


When a **dependent new case** is created by clicking New and then Dependent case, following information is filled in automatically based on the selected case in the case list:
- **Name** from General pane
- **Parent case** in General pane is automatically populated
- **Everything** from Loss Event pane

**Automatically populated data can be changed manually**.

## Loss event statuses and stages

Loss event functionality uses standard case statuses and case stages functionalities.

Loss event can be in one of 4 following statuses:
- **Opened**
- **In process**
- **Closed**
- **Cancelled**

In addition to statuses, stages of loss event can be also monitored. List of stages depends on the selected Case process. 

The **Case process** button enables editing the case process that is selected on the loss event. The **Change stage** button enables moving from one stage to another in the case process. To start a next stage and complete the previous one, mark the first case in the list with the status Not started and click the button OK.

Although it does not influence entering data in any field, tracking stages of the loss event can be helpful with loss events that last over some period. Whenever a user reopens the loss event, it can be easily checked in which stage is the loss event.

## Details view

When a new case is created (or an already created one is opened), Details view is opened, where all the information about the loss event can be found. 

**General** and **Loss event** fast tabs contain:
- Information added throughout the pop-up panes **General**, **Loss event** and **Other** 
- Additional standard case follow-up fields, such as Email ID, Contact ID, etc.
- **Billing project** (General fast tab) – if a project will be used for the purpose of posting project transactions related to remediating the damage in order to track costs, that project can be linked to a loss event by selecting it in the Billing project field. 
- **Invoice amount** (General fast tab) – shows the sum of all vendor invoices linked to the loss event in Associations fast tab.

The **Insurance coverage** fast tab enables adding insurance entities that are included/damaged/injured in loss event. The selection is limited to insurance entities that were added on insurance policy, which is selected in the loss event. 

The **Insurance company** fast tab enables adding different loss event information throughout the process:


| Field                                   | Description                                                                                                                                                                                                                                                                                                                                          |
|-----------------------------------------|------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|
| **Notification date of the loss event** | The date of reporting the loss event to the insurance company                                                                                                                                                                                                                                                                                        |
| **File ID**                             | The ID of the document, which was used for reporting the loss event to the insurance company                                                                                                                                                                                                                                                         |
| **Settlement date**                     | The date when insurance company finishes with the settlement process                                                                                                                                                                                                                                                                                 |
| **Remittance date**                     | The date when the insurance company pays the damage amount                                                                                                                                                                                                                                                                                           |
| **Payment ID**                          | User can manually insert Payment ID when the insurance company transfers the money for damage remediation                                                                                                                                                                                                                                            |
| **Remittance amount**                   | The amount payed by the insurance company                                                                                                                                                                                                                                                                                                            |
| **Damage assessment**                   | Once the damage is assessed, the damage assessment amount can be entered in this field manually. If the **Calculate damage assessment** button is clicked, damage assessment amount is calculated as a sum of all **confirmed project quotations** connected to the billing project selected in the General fast tab, as shown in the example below. |
| **Total damage assessment**             | Total damage assessment is calculated after the changes in damage assessment field with standard D365FO refresh button. Total damage assessment amount includes damage assessment of the case and the sum of all total damage assessments on dependent cases/child loss events (if applicable).                                                      |
| **Deductible franchise**                | This amount is copied from the Insurance policy selected in the General fast tab                                                                                                                                                                                                                                                                     |
| **% deductible**                        | This amount is copied from the Insurance policy selected in the General fast tab                                                                                                                                                                                                                                                                     |
| **Deductible type**                     | Drop-down field with values Amount and Percent. Based on the selection, system is considering either Deductible franchise field or % deductible field.                                                                                                                                                                                               |
| **Total deductible franchise**          | If **Deductible type** is **Amount**, value from field **Deductible franchise** is copied. If **Deductible type** is **Percent**, then **Total deductible franchise = Granted damages * (% deductible / 100)**.                                                                                                                                      |
| **Estimated granted damages**           | Once the estimation of granted damages can be made, the amount is entered in this field.                                                                                                                                                                                                                                                             |
| **Granted damages**                     | Once the insurance company confirms the amount of granted damages, the amount is entered in this field                                                                                                                                                                                                                                               |
| **Amount paid**                         | **Amount paid = Granted damages – Total deductible franchise**                                                                                                                                                                                                                                                                                       |

In addition, standard D365FO case fast tabs **Service level agreement, Case log, Associations, Knowledge article** and **Administration** are available.

**Administration** fast tab provides information about opening and closing the loss event. In **Closure reason** field prior to changing the loss event status to Closed, Closure reason can be chosen based on code list of closure reasons defined in **Fixed assets > Setup > Insurance > Closure reasons**.

## Mass closing of loss events

Mass closing functionality changes status for all marked cases from In process to Closed. 

When the button Mass closing is clicked, new pop-up is opened, where the Closure reason field is available. Closure reason field is a drop-down field with closure reasons defined in **Fixed assets > Setup > Insurance > Closure reasons**.

If cases with other statuses (Open, Closed, Cancelled) are marked for Mass Closing, there is a message stating that mass closing is not allowed for such statuses. 

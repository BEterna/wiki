The following subchapters describe Investment management project enhancements, which are:
- Project subtype for separate investment and implementation project hierarchies based on selected Project group at project creation
- Project numbering based on selected Project group at project creation
- Defaulting of Sales price group on a project based on selected Project group at project creation
- Defining Project sort fields in hierarchy at selection on a project from a code list
- Selecting Project purpose for e.g. project objectives, closure reason etc.
- Defining Financing types in a time interval for reporting purposes
- Ability to link different project hierarchies for investment projects.

# Project group
---
Investment management provides the ability to configure additional fields on Project groups that are defaulted to a specific project during the creation of new records. New fields are:
- Project subtype
- Number sequence
- Sales price group.

## Project subtype

Project subtype is used to separate project hierarchies (Implementation and Investment) for the Investment project type. There are three different project subtypes:
- **Investment**: it is used for projects, which represent investments and project categories, which are used for posting and reporting purposes, can differ from project categories that are used for implementation projects. 
- **Implementation**: it is used for projects, which represent work orders and it is usually used for more detailed reporting purposes comparing to investment project hierarchy. 
- **Default**: used for any other projects that do not require separate implementation and investment project hierarchies.

Projects with the Implementation subtype are mapped to the projects with the Investment subtype based on the Projects linking and Projects category mapping setup. All transactions posted to implementation projects must be firstly activated to the investment project(s), before they can be activated to fixed asset(s).

## Number sequence

Projects are numbered based on the setup in Project management and accounting parameters. Additional option is available for project numbering on the Project group setup. In order for this option to be available in the Project group form, we must firstly enable the **Use number sequence from project groups** parameter in _Project management and accounting parameters_. 

When this option is enabled, it is possible to set configured number sequence on Project group. When we create a new project with a project group that includes configured number sequence, such project will have a project ID corresponding to configured number sequence. 

## Sales price group

With Investment management package, Price group can be defaulted on Project groups. Field Sales price group is available on the Project group entity, if the parameter **Use price group from project group** is enabled in _Project management and accounting parameters_.

When we create a project using such project group, Sales price group is defaulted to Project, tab Setup, field Sales price group, and can be modified, if required.

# Project sort fields
---
In contrast to standard functionality, with Investment management package, Project report sort fields can be configured **in hierarchy**. For this purpose, set the parameter **Use hierarchical project report sort fields** option to **Yes** in _Project management and accounting parameters._ 
 
With this parameter set to Yes, setup of Project report sort fields can be done in hierarchy. In _Project management and accounting > Setup > Projects > Project report sort fields_ additional column, named **Parent field**, is available (if the parameter is set to Yes) with which a hierarchy between sorting fields can be configured. With parent sort fields, we cannot configure Sort field 2 or 3 without a Parent field. System will warn us when trying to save such record with a warning "Non-first level sorting must have a parent". 

It is possible to update Project report sort fields via the Projects data entity. 

Using Sorting fields on Project entity means that if a parent is selected in Sort field 1, the values in Sort field 2 will be filtered to show only child values of Sort field 1. If only Sort field 3 is selected, sort fields 1 and 2 will automatically populate. Project sort fields can also be added to the all project list page by personalizing the table with Add columns functionality.

# Project purpose
---
Project purpose is additional field available in the Project entity and it can be used for **different reporting purposes**, e.g. reason for project closure, project objectives, project area etc. Project purpose field is available on project under the General tab. Users can also personalize this field on the list of all projects.

A code list of project purposes is available in the _Project management and accounting > Setup > Projects > Project purposes_. Code list is defined by users (length limit of purpose code is 10 characters). To add new purpose code simply select New and in order to Delete existing one, click Delete. If we try to delete a purpose code that is already used by any project, error will pop up. In such cases, we must firstly change or remove purpose code on the project entity and removal from code list will afterwards be possible.

# Financing types
---
The Financing types code list is available in _Project management and accounting > Setup > Projects > Financing types_ and it is defined by users. 

In order to define financing types on project, select a project and go to the _Manage tab > Related information > Financing types._ In the new window, you define financing type, amount and period. This information can be used for reporting purposes. If we are trying to add the same financing type for different period, such record will be time sliced. System will notify us about over-layering, and it will automatically set the date in the To date field.

If we try to delete a type that is already used by any project, error will pop up. In such case, we firstly must change or remove a record on the project entity and removal from code list will afterwards be possible.

# Projects linking
---
This functionality allows creating the **link between investment and implementation** projects if separate hierarchies are required. In order to link different projects (e.g. work orders linked to an investment project), go to _Project management and accounting > Setup > Projects > Projects linking._ Firstly, an implementation project must be defined in the _Implementation project_ field, then the investment project desired to be linked with the implementation project can be defined in the _Investment project_ field. Implementation and Investment project names are populated automatically after saving selected records and cannot be changed in this form.

# Project category mapping
---
Project category mapping setup is located in _Project management and accounting > Setup > Categories > Project category mapping_. This setup is used for mapping project categories during the Activation of implementation project transactions to investment projects. 

Project category mapping table contains following fields:
- **Project selection**: it can be Table, Group or All. Project category mapping can be on a project, project group or all projects level. If Project selection is Table, then specific project can be selected in the From project field. If Project selection is Group, then specific project group can be selected in the From project group field. If Project selection is All, the line is valid for all projects.
- **From project**: if Project selection is Table, then specific project can be selected in the From project field. The line is valid only for the project that is selected in this field.
- **From project group**: if Project selection is Group, then specific project group can be selected in the From project group field. The line is valid only for the project group that is selected in this field.
- **Category selection**: it can be Table, Group or All. Project categories can be mapped on a project category, project category group or all projects categories level. If Category selection is Table, then specific project category can be selected in the From category field. If Category selection is Group, then specific project category group can be selected in the From category group field. If Project selection is All, the line is valid for all project categories.
- **From category**: if Category selection is Table, then specific project category can be selected in the From category field. The line is valid only for the project category that is selected in this field.
- **From category group**: if Category selection is Group, then specific project category group can be selected in the From category group field. The line is valid only for the project category group that is selected in this field.
- **To category**: this project category represents a category in which is implementation project transaction mapped after the activation of implementation project transaction to investment project. Note that To category can only be a category that has Expense transaction type.

Note that the more specific setup has a priority (e.g. Line on the project level has a priority over a line on the project group level, line on the From category level has a priority over a line on the From category group level).


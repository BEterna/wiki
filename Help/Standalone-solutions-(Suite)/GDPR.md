## **About**
In D365FSCM tables there is some data stored, which is according to the definition of the General Data Protection Regulation (GDPR) or the Personal Data Protection Act (hereinafter referred to as ZVOP-2), qualify as personal data. This includes either data of the company employees or business partners (persons) which buy from or sell to the company products and services. System recognizes persons by the record type in the Global Address book.
The company is obligated to adequately protect personal data that is processed and comply with the requirements of Slovenian and EU legislation. Part of fulfilling these legal requirements is enabling traceability of data processing or an audit trail. 
Because of these reasons it is necessary to provide a technical solution in the Microsoft Dynamics D365FSCM system, that will allow the generation of an audit trail concerning predefined data and associated events.

## **Setup**
System Administration > Settings > GDPR.
<br><br>The user role allowed to modify the settings for logging access to personal data is called GDPR-manager. The user role is appropriately assigned to a user or user group, depending on the company's policy.
<br><br>System Administration > Settings > GDPR > GDPR Entities.
<br><br>In action pane go to Entities. There are 3 options (buttons):
-	Refresh entities – with this button user will create entity list for the first time and should be also used if new entities are added for the project.
-	Enable all entities – with this button user will set Enabled option to Yes on all entities.
-	Disable all entities – with this this button will disable option Enabled on all entities. 

For every entity individual fields must be defined for which company wants to log accesses. If any user views or uses data of an entity, or if the system had to load them due to some user action, it will be recorded that the user has seen all the specified fields. 
<br><br>New fields can be added to the logging list using the "New" button. 
<br><br>Logging is defined for:
-  Field Name - from the dropdown list, we can choose the relevant fields for which we will log accesses. 
-	Description - it is copied from the dropdown list "Field Label." 
-	Additional Description - when multiple options are hidden under one field, we can select which options will have their accesses logged.

## **About**
Within D365FO implemented in the company, databases are generated and stored, which also contain data that, according to the definition of the EU General Data Protection Regulation (GDPR) or additional local regulations, qualify as personal data. This includes either data of the company's employees or data of clients/customers of the products and services provided by the mentioned company. 

Local regulations supported in this solution are:
- Slovenian Personal Data Protection Act (hereinafter referred to as ZVOP-2)

The company is obligated to adequately protect personal data that is processed and comply with the requirements of EU and local legislation. Part of fulfilling these legal requirements is enabling traceability of data processing or an audit trail. 

This solution enables the system to recognize persons by the record type in the Global Address book and generates an audit trail concerning predefined data and associated events.

## **Setup**
_System Administration > Settings > GDPR._
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


## **Entities included in the base package**
_System Administration > Settings > GDPR logging > GDPR Entities._
<br><br>The following entities are included in the suite package (on which the logging of the audit trail for specific fields can be configured):<br>
- ContactPerson - Contacts
- CustBankAccount – Customer bank accounts
- CustCollectionLetterJour – Collection letter journal
- CustInvoiceJour – Invoice journal
- CustInvoiceTable – Free text invoice
- CustTable – Customers
- DirPartyPostalAdressVeiw – Partner addresses
- DirPerson – Individuals
- DirPesonName – Person's name
- HcmEmployment – Employment
- HcmEmploymentDetail – Employment details
- HcmEmploymentEmployee – Employee details
- HcmPersonalContactRelationship – Personal contacts
- HcmPersonaIdentificationNumber – Person's identification numbers
- HcmPersonPrivateDetails – Personal details
- HcmWorker - Worker
- HcmWorkerBankAccount – Worker's bank account
- LogisticElectronicAddress – Communication data – electronic address
- LogisticsEntityPostalAddress – Postal address overview
- LogisticsLocation - Locations
- LogisticsPostalAddress - Addresses
- LogisticsPostalAddressView – Address overview (Address View)
- VendBankAccount – Vendor bank accounts
- VendTable – Vendors

All these entities in D365FCSM are identified as containing personal data of individuals. If the company wishes to add additional entities to the list, this can be done as an additional extension within the project. 
<br><br>For each entity logging rules are implemented to track: 
- Insert - visible in the audit trail as an add action 
- Delete - visible in the audit trail as a delete action 
- Update - visible in the audit trail as an edit action 
- Post load and post cache load - visible in the audit trail as view actions

**NOTE:** If additional entities are added by a customization, it is necessary to refresh the overview, and this can be done by clicking the "Refresh entities" button on the entities tab.


## **Preventing duplicate view logging**
_System Administration > Settings > GDPR > GDPR parameters._

Within the GDPR parameters, there is a setting in the General tab that allows us to prevent duplicate logging of views if a repeated view occurs within a certain time period. 

When a user opens a specific entity twice, duplicate records are created in the audit trail. The setting "Rejecting duplicates" allows us to eliminate duplications within a specified period if the "Enabled" setting is set to Yes. 

The Expiration type can be:
- Absolute - checks for duplicate records in a constant period (in seconds).
- Sliding - checks for duplicate records in a sliding period (in seconds) based on the start of the user's activity.

The "Seconds" setting allows us to define the period in which we want to check for duplicate records. The time period is specified in seconds, which means that, if set to 30, viewing the same entity twice within 30 seconds will not be logged as duplicate accesses.


## **Configuration**
_System Administration > Settings > GDPR > GDPR parameters._

The configuration is the same for all companies. It requires loading from an XML file. Options for export are: 

- Writing to an external SQL database
- Other options for storing audit trail data are described in the link: 
   - https://github.com/NLog/NLog/wiki/Targets  (as of April 14, 2021) 
   - SysLog documentation is available at https://github.com/luigiberrettini/NLog.Targets.Syslog. 


Among other data in the XML configuration, we can find information about: 
- Table name 
- Server
- User
- Password

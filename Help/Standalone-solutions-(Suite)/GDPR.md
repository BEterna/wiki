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
## **Entities included in the base package**<br>
System Administration > Settings > GDPR logging > GDPR Entities.<br><br>The following entities are included in the suite package (on which the logging of the audit trail for specific fields can be configured):<br>
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
<br><br>For each entity, a "class" must be developed with implemented logging rules and implemented calls to five "methods" on the entity:
- Insert - visible in the audit trail as an add action 
- Delete - visible in the audit trail as a delete action 
- Update - visible in the audit trail as an edit action 
- Post load and post cache load - visible in the audit trail as view actions

**NOTE:** If additional entities are added later, it is necessary to refresh the overview, and this can be done by clicking the "Refresh entities" button on the entities tab.

## **Preventing duplicate view logging**<br>
System Administration > Settings > GDPR > GDPR parameters.

Within the GDPR parameters, there is a setting in the General tab that allows us to prevent duplicate logging of views if a repeated view occurs within a certain time period. 


When a user opens a specific entity twice, duplicate records are created in the audit trail. The setting "Rejecting duplicates" allows us to eliminate duplications within a specified period if the "Enabled" setting is set to Yes. 

The Expiration type can be:
- Absolute - checks for duplicate records in a constant period (in seconds).
- Sliding - checks for duplicate records in a sliding period (in seconds) based on the start of the user's activity.

The "Seconds" setting allows us to define the period in which we want to check for duplicate records. The time period is specified in seconds, which means that, if set to 30, viewing the same entity twice within 30 seconds will not be logged as duplicate accesses.

## **Configuration**<br>

System Administration > Settings > GDPR > GDPR parameters.

The configuration is the same for all companies. It requires loading from an XML file. Options for export are: 

- Writing to the database - recommended for testing on UAT (for testing purposes, it writes to DW [data warehouse] on the UAT database) -> [companyGDPR].[GdprLog]
- Other options for storing audit trail data are described in the link: https://github.com/NLog/NLog/wiki/Targets  (as of April 14, 2021) 
- SysLog documentation is available at https://github.com/luigiberrettini/NLog.Targets.Syslog. 


Among other data in the XML configuration, we can find information about: 
- Table name; example for UAT = Database name="dbo" 
- Server; 
- User; example for UAT = User ID= company_GDPR_D365_UAT; 
- Password; 

Below find fields that are exported to database or to some other location:

|Seq.|Field|Example|Field explanation|
|--|--|--|--|
|1|EventID |37538|Sequential record number|
|2|Eventname|SmartZVOP|Event name, always the same|
|3|Eventtime|2021-03-01 13:43:48.000|Time of the event|
|4|DomaineName|COMP|Domain name|
|5|Username|GMBERNARDA|User code, Code of the user who accessed personal data|
|6|Fullname|Bernarda GM Be-Terna|Full name of the user who accessed personal data|
|7|appname|MsDyn365FO|Application name through which data was accessed, for example, in case of D365FSCM, it will be recorded as MsDYN365FO|
|8|modename|WebClient|Access = in case of D365FSCM = WebClient|
|9|coreidzvop|000012408|ID of the person in Global address book whose data was accessed|
|10|namezvop|PETER|First name of the individual whose data was accessed| 
|11|surnamezvop|ELEKTRIČAR|Surname of the individual whose data was accessed|
|12|birtdayzvop|1900-01-01|Birthday of the individual whose data was accessed, in the format yyyy-MM-dd; if the data is not available, the system returns: 1900-01-01| 
|13|addresszvop|Mariborska cesta 1 2000 MARIBOR SVN|Address of the individual whose data was accessed; if the data is not available, the field is empty|
|14|taxzvop|76161846|Tax number of the individual whose data was accessed; if the data is not available, the field is empty|
|15|pidzvop|0505999500336|Personal Identification Number (EMŠO) of the individual whose data was accessed; if the data is not available, the field is empty|
|16|actionzvop|View|User action, possible values are View, Edit, Add, Delete|
|17|purposezvop|CustTableListPage – Display|Display Form name through which the user accessed personal data – and its type|
|18|infozvop|First name Last name|Fields the user accessed|
|19|aosinstance|Azure|Instance, for example, Azure|
|20|tablename|DirPersonName|Name of the table/entity whose data was accessed. Names are listed in section Entities included in the base package|
|21|loguseralias|FirstName.LastName@company.com|E-mail address recorded on the user accessing this data|
|22|systemname|COMP-UAT|In the case of access from D365FSCM = D365FO environment from which the access occurred|
|23|logform|CustTable|Form name through which the user accessed personal data|
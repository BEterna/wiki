##**Setup**
---
###**Case categories**
Organizational administration/Setup/Cases/Case categories/
1.	Use the »New« button to generate a new case category. Define case category, description, category type and worker.
2.	Save
###**Enforcement settings**
Credit and Collections/Setup/Enforcements/Enforcements settings/General
Web service setup
|**Parameter**|**Description**|**Value (for test server)**|
|--|--|--|
|**Web server for sending**| Web server for submitting the enforcement packets to court|https://evlozisce-test.sodisce.si/axis2/services/PackageProposalService
|**Web server for checking**|Web server for checking the enforcement packets with the|https://evlozisce-test.sodisce.si/axis2/services/ProposalStatusService
|**Enforcement proposal electronic reporting format**|Enforcement proposal electronic reporting format (XML)|Enforcement proposal format (Electronic reporting)

Note: Prior to selecting the Enforcement proposal electronic reporting format in enforcement settings, it needs to be configured in Electronic reporting workspace. Configure a new repository with a Configuration repository type: »Adacta Suite (Dunning)« and import the contained electronic reporting formats. 
Links for web servers can be found on https://evlozisce.sodisce.si/ . 

Credit and Collections/Setup/Enforcements/Enforcements settings/Payment
|**Parameter**|**Description**|**Value**|
|--|--|--|
|**Vendor account**|Possible to generate vendor invoice with the selected vendor account|Any vendor|
|**Procurement category**|Unique ID for the record in the database|Procurement category for Court fees|
|**Unit**|Unit of measure|Any value|
|**Payment method**|Fee payment method|Any value – 3 options explained below|

Payment method:
-	**Packet** – summed for the whole package,
-	**Proposal** - separately for each enforcement proposal (in this case paying court fee on a package level is disabled) or
-	**Packet or proposal** – both (separate or packet court fee payment) options stay available, user can decide about the desired payment option later.

###**Courts**
Credit and Collections/Setup/Enforcements/Courts
List of Slovenian courts (SIF classification) can be found on: 
http://www.sodisce.si/mma_bin.php?static_id=20180809130818

Values to be added are:
|**Field**|**Description**|
|--|--|
|**Court ID**|Court ID as stated in the link data|
|**Court name**|Name of the court as stated in the link data|
|**Street**|Court address – street name and house number|
|**City**|Court address - city|
|**ZIP/postal code**|Court postal code|

###**Cadastral municipalities**
Credit and Collections/Setup/Enforcements/Cadastral municipalities
List of Slovenian cadastral municipalities can be found on:
https://www.stat.si/Klasje/Klasje/Tabela/6415 

Values to be added are:
|**Field**|**Description**|
|--|--|
|**County**|Cadastral municipality code|
|**Description**|Name of the cadastral municipality|
|**Court name**|Select or entre court ID to which this cadastral municipality belongs to|

###**Number sequences**
Organizational administration/Number sequences/Number sequences
Create two new number sequences. In the reference section for each of the newly generated sequences, select:
-	Area: »Dunning (Adacta)«,
-	References: »Enforcement proposal ID« or »Enforcement packet ID« - one for each of the two number sequences.


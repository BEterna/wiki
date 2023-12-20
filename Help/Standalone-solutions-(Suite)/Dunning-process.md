# Dunning

The package covers two important dunning processes. First is automated generation of collections cases and the other are enforcements, that cover the judicial dunning procedure including communication with court. 
With collections cases users can follow activities that have been performed by collections agents internally in order to collect open receivables. As part of this package, mass generation of collections cases has been enabled. 
Second functionality covers judicial dunning procedure. Collections cases can represent input for enforcements, but enforcements can also be used independently.  Enforcements represent second step of dunning process and are used when internal collection process does not result in collected receivables, so they need to be collected through court. 

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
|Web server for sending| Web server for submitting the enforcement packets to court|https://evlozisce-test.sodisce.si/axis2/services/PackageProposalService
|Web server for checking|Web server for checking the enforcement packets with the|https://evlozisce-test.sodisce.si/axis2/services/ProposalStatusService
|Enforcement proposal electronic reporting format|Enforcement proposal electronic reporting format (XML)|Enforcement proposal format (Electronic reporting)

Note: Prior to selecting the Enforcement proposal electronic reporting format in enforcement settings, it needs to be configured in Electronic reporting workspace. Configure a new repository with a Configuration repository type: »Adacta Suite (Dunning)« and import the contained electronic reporting formats. 
Links for web servers can be found on https://evlozisce.sodisce.si/ . 

Credit and Collections/Setup/Enforcements/Enforcements settings/Payment
|**Parameter**|**Description**|**Value**|
|--|--|--|
|Vendor account|Possible to generate vendor invoice with the selected vendor account|Any vendor|
|Procurement category|Unique ID for the record in the database|Procurement category for Court fees|
|Unit|Unit of measure|Any value|
|Payment method|Fee payment method|Any value – 3 options explained below|

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
|Court ID|Court ID as stated in the link data|
|Court name|Name of the court as stated in the link data|
|Street|Court address – street name and house number|
|City|Court address - city|
|ZPI/postal code|Court postal code|

###**Cadastral municipalities**
Credit and Collections/Setup/Enforcements/Cadastral municipalities
List of Slovenian cadastral municipalities can be found on:
https://www.stat.si/Klasje/Klasje/Tabela/6415 

Values to be added are:
|**Field**|**Description**|
|--|--|
|County|Cadastral municipality code|
|Description|Name of the cadastral municipality|
|Court name|Select or entre court ID to which this cadastral municipality belongs to|

###**Number sequences**
Organizational administration/Number sequences/Number sequences
Create two new number sequences. In the reference section for each of the newly generated sequences, select:
-	Area: »Dunning (Adacta)«,
-	References: »Enforcement proposal ID« or »Enforcement packet ID« - one for each of the two number sequences.

###**Enforcement proposal template**
Credit and collections/Enforcements/Enforcement proposals (button Template)

To simplify day to day operations, enforcement template can be created. This template will be used when creating new enforcement proposals. In the template user can predefine all data that is common to new enforcement proposals. The data used in the template can be later changed in the enforcement proposal. 

Suggested common data, defined on the template:

|**Tab**|**Field**|**Description**|
|--|--|--|
|General|Billing classification|Select or enter billing classification that will be used for charging customer for| 
|General|Reference ID formatting|String that formats payment reference, where %1 is replace by proposal ID and %2 by customer account|
|General|Legal interest (Yes/No)|Are legal late interest available?|
|Participants|Table of data|Roles creditor, representative and depositor are usually same for all new enforcements. Each line in the table has own Details below. For creditor tab bank account should also be defined.|
|Suggestions|Table of data|In this table it can be defined usual means for transaction repayment, such as cash equivalents (money on bank account) or regular income…|
|Creditor cost|Table of data|Table of cost type where setup for Free text invoices and pending vendor invoices can be set (with Yes/No option for Legal interests).|
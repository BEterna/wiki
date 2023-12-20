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

**Payment method:**
-	**Packet** – summed for the whole package,
-	**Proposal** - separately for each enforcement proposal (in this case paying court fee on a package level is disabled) or
-	**Packet or proposal** – both (separate or packet court fee payment) options stay available, user can decide about the desired payment option later.

Introduction
This document serves as a guideline through the additionally developed features, which allow users to efficiently conduct public procurement processes. Public procurement is a set of actions, with an objective of purchasing goods, services or contractual works in a more economical way. In some countries, the use of prescribed public procurement procedures is often mandatory, especially for direct or indirect users of national and local budgets. Regardless of the type and extent of the order, these entities must respect the fundamental principles of public procurement, such as the economic use of public funds, the equity of providers, the transparency of the procedures, and the principle of ensuring competition between the tenderers. All public procurement contracts have to be in accordance with these principles, therefore this functionality enhances and adds to the standard D365O functionality for the purpose of simple, efficient and legally correct public procurement.
Throughout the following sections of this document, functionalities and forms connected with different public procurement procedures will be presented, together with their embeddedness with the standard D365O features, required for public procurement processes. The main purpose of this document therefore is to present how public procurement is performed in D365O.
Firstly, the required setup in terms of public procurement is described, followed by the overview of public procurement procedures and the role of additionally developed functionalities (Public procurement case enhancements and Framework agreements) in these procedures. Additionally, enhancements added to standard D365O forms (e.g. purchase orders or requests for quotation) are presented throughout the document.













1.	Public procurement parts
Public procurement parts refers to requests for quotation (RFQ) cases, which are used as input documents to successfully perform public procurement procedures. Throughout the following chapter, required setup, prerequisites and additionally developed functionalities, required for an adequate RFQs creation for the purpose of public procurement procedures are presented.
1.1	Request for quotation case enhancements
RFQ cases are used as inputs (parts) of public procurement cases, described in the following chapter (2). Although RFQ cases are standard D365O functionality, some additional enhancements are added for the purpose of public procurement procedures. These enhancements are described throughout the following paragraphs.
Public procurement functionality adds the “Public procurement” section in the RFQ case header. This section contains »Case ID« and »Description« fields, which are populated with the public procurement case ID and description once RFQ case is connected with the procurement case. Additionally, information in the »Expected date of finality« and »Final« checkmark display information about the connected case finality:
 
Once created, RFQ cases can be added to either a new or an existing public procedure case, using the “Create case” or “Add to case” actions: 
 
If RFQ case is to be connected to a public procurement case, its purchase type should be either “Purchase order” or “Purchase agreement”, depending on the desired document, created because of the related public procurement case.
 
For the purpose of public procurement procedures in D365O, RFQ cases should only contain lines with the ordering goods/services. Proposed vendors should not be defined directly on each RFQ case, but directly on public procurement case, which is described later throughout this document (chapter 2.4.8). 
All other processes (e.g. sending RFQs or entering vendor replies to RFQ cases) are also performed directly from the public procurement case and are not supposed to be performed through RFQ case form.
2.	Public procurement cases
Public procurement cases functionality is used to perform public procurement procedures in D365O.
2.1	Setup
2.1.1	Case categories
Organization administration/Setup/Cases/Case categories
Case categories are used to distinguish between different public procurement procedures. The required number of case categories therefore depends on the types of distinct public procurement processes required to be performed in D365O. For each public procurement procedure (e.g. Low value order or Open procedure), a unique case category is proposed to be created.
New Case categories can be created by clicking »New«, then entering name and description to an adequate hierarchy node. For each case category, a default case process can be set. Case processes specify the steps for each distinct public procurement process and are further described throughout the following chapter (2.1.2).
In “Public procurement amount limits” section, order value for each public procurement case category can be set. Amounts refer to the total amount of the combined public procurement case parts (RFQ cases), added to the case. However, no amount validation exist, while these amounts are mainly informational.
 
If total amount of the combined RFQ cases connected with the public procurement case is lower or exceeds the defined amount limits, “Amount status” field in “General” section of the public procurement case displays information about the low or exceeded limit.
 
Additionally, amount limits are checked, if “Propose case categories” function is used when adding RFQ cases to a new public procurement case.
 
2.1.2	Case processes
Organization administration/Setup/Cases/Case processes
Case process is a predefined template, which describes the expected steps in the process of each of the public procurement cases. Case processes can be defined per case category or separately for each public procurement case.
A new case process can be created by clicking “New” and adding responsibilities – a list of all the possible stages within the process.
 
Once Responsibilities are entered, process hierarchy can be defined. This is done by clicking “Details” button under “Process” tab.
 
Hierarchy of the entered process steps can be added by clicking “New” - “Level”. A new form opens, where additional information about each of the step in the process can be entered.
 
2.1.3	Case Statuses and Stages
When newly created, public procurement case is in status “Opened”. When users start working with the case, status can be updated to “In process” by clicking “Change status” button.
 
Additionally, public procurement case stages indicate in which part of the public procurement procedure case currently is. These stages serve only as information for the case users. Thus, no validation connected with each of the case stage exists. Setup of the public procurement case stages is described in chapter 1.2.1.
 
Each stage of the case can be started by clicking »Change stage« and selecting the applicable stage. For example, »Public procurement members« stage should be proceeded once, the adequate members have been added to the Public procurement case.
 
NOTE: both – Public procurement case statuses and stages only have the informational value for users - e.g. to get an insight into stage of the public procurement or easily filter out the desired public procurement cases. However, no validation linked with either specific public procurement case status or stage exists.
2.2	Create case
Public procurement cases can be created:
(1)	Directly from the RFQ case
On RFQ case click on either “Create case” (creates a new public procurement case) or “Add to case” (connects RFQ case with an already existing public procurement case) button:
 
(2)	Through Public procurement cases form
Procurement and sourcing/Public procurement cases/All cases
Click on “New” - “Case”.
 
Following any of the above described procedures (1 or 2), a new form opens. If action to add RFQ case to an already existing case is selected, a new form opens, where users can select the public procurement case, with which they want to connect the RFQ case.
If an action to create a new public procurement case out of RFQ case is selected, a different form opens, where it is possible to determine additional information about the public procurement case. This information is described below by each section of the public procurement case form.
GENERAL
 
-	Name: selected from the workers and contractors register (used to ease the filtering of cases);
-	Case category: select an adequate public procurement case category from the register (setup described in chapter 1.1.1);
-	Case ID: generated automatically according to the number sequences setup;
-	Description: description (content) of the public procurement case can be added;
-	Priority: can be selected from the register;
-	Parent case: an existent public procurement case can be selected if applicable;
-	Status: can be selected from the register.
PUBLIC PROCUREMENT
 
-	Purchase type: the desired result of the public procurement case (Purchase agreement, Purchase order or Framework agreement);
-	Solicitation type: selected from the register (Constructions, Goods or Services);
-	Expiry date and time: expiry date of the Public procurement case (final date for the acceptance of vendor quotations);
-	Subject: a free text field (e.g. longer description of the public procurement case);
-	Agreement ID: link to an associated Framework agreement if it exists.
OTHER
 
-	Department: department responsible for the public procurement case;
-	Employee responsible: an employee responsible for the public procurement case (selected from the employees register);
-	Case process: populated automatically according to case category (defined in “General” section) – it can still be changed by selecting an adequate value from the register.
After all the required information for a specific public procurement case is entered, case can be created by clicking »Create« button in the bottom right corner of the form. A public procurement case form opens, where most of the information, entered upon creating the case can still be edited. Public procurement case form and its processing is described throughout the following chapter.
2.3	Case sections
Throughout the following part of the document, sections of the Public procurement case form, together with their purpose and functionalities are described.
2.3.1	General
General section consists of mostly the information, which can already be entered upon creating a new public procurement case (as described in chapter 2.2.). Additionally, a Primary contact connected with the case can be selected from the contacts register.
 
2.3.2	Public procurement parts
This section consists out of the RFQ cases, related to the public procurement case. If public procurement case has been created directly from the RFQ case (as described in chapter 2.2 – (1)), RFQ number from which public procurement case has been created is automatically displayed in the public procurement parts sections. On the other hand, if public procurement case has been created throughout the Public procurement cases form (as described in chapter 2.2 – (2)), RFQ case(s), which the user wants to associate with the public procurement case need to be manually added. This can be done by clicking on the »New« button. Details about each of the related RFQ cases can be viewed by clicking on the »Details« button, which opens the selected RFQ case. By clicking “Delete” button, RFQ case(s) can also be removed from the public procurement case.
 
ID of the connected RFQ case(s), their Title and Net amount are automatically transferred from each RFQ case when they are added to the public procurement case.
Additionally, Expected dates of finality and a checkmark whether quotations in relation to each RFQ are Final can be specified. Their function is described later throughout the document.
2.3.3	Public procurement members
In this section, it is possible to add members (e.g. of the Expert commission), related to the public procurement case. This can be done by clicking »New« and selecting adequate member roles (from the register of roles), then assigning each role to a worker (from the register of workers). For each of the selected members, a Description and duration of their membership in the public procurement case can be defined. Multiple members can be added (as separate lines).
 
2.3.4	Public procurement attachments
Attachments can also be added to the Public procurement case. This can be done by clicking »New« and selecting the present attachment type from the register. Once a new line is created, desired files to be attached (e.g. service/goods specifications, different documentation) can be added to each line, by clicking the »Attachments« button.
  
A new (standard) form opens where a file type can be selected, uploaded  and other details about the attached file can be filled in. 
 
2.3.5	Public procurement identifications
Once public procurement case is officially published on an adequate public procurement portal, Public procurement identifications (št. Javnega naročila) can be entered.
  
2.3.6	Certifications
Additional enhancement on certifications is added as part of public procurement functionality, and that is Certification insurance type. Upon certification entry on vendor form, the field Cerification insurance type is added to the standard form to ensure additional classification of vendor ceritifcates. 
 
The values for drop-down selection in this field are entered in the code list at Procurement and sourcing > Setup > Vendors > Certification insurance type.
 
If certifications are applicable for an individual public procurement case, they can be added in this section by clicking “New”, specifying Vendor (it is possible to choose from all the tenderers, co-tenderers or subcontractors specified in “Tenderer registration section” of the public procurement case) and selecting Certification type from the related register.
  
One vendor certificate can only be used for one public procurement case. It is not possible to use the same certificate on multiple cases.
2.3.7	Proposed vendors
Proposed vendors section is used only for public procurement procedures, connected with a Framework agreement. If Framework agreement is linked to a Public procurement case, Proposed vendors section displays vendors (tenderers) from the related agreement. If public procurement is not linked to a Framework agreement, proposed vendors should not be entered.
 
2.3.8	Tender registration
Tender registrations section serves for registering tenders, who responded to the specific public procurement request. The following fields are available to be entered for each tender (line):
-	Date and time: of the received tender;
-	Vendor’s account: vendor’s account from the vendor’s register (NOTE: if vendors are added to “Proposed vendors” section of the public procurement case, only these specified vendors can be selected when registering tenderers);
-	Consortium: should be checked if line refers to the consortium of vendors;
-	Worker: who registered the tender is automatically selected from the register upon entering each new tender;
-	Delivery status: indicates whether tender has been received within the specified public procurement case Expiry date - “Late” or “In time” options are available (NOTE: only tenders from the tenderers who sent their tenders “In time” can be accepted later in the process);
-	Submission method: indicates the method by which tenderer has submitted the tender (e.g. by mail or electronically);
-	Delivered by: a free text field (e.g. name of the delivery person); 
-	Properly labelled: indicates whether the received tender is properly labelled (NOTE: only properly labelled tenders can be accepted later in the process);
-	Number of consignments: indicates the number of the received consignments connected with the tender.
 
In the bottom part of the form, users can specify to which RFQ case from the “Public procurement parts” each tender reefers to. Bottom part of the form consist of as many lines as there are RFQ cases (public procurement parts) related to the public procurement case.
For example – tender from “Telekom Slovenije, d.d.” refers to the goods/services from public procurement part “000076”. This is indicated with the “In tender” checkmark:
 
1.1.1.1.	Consortium
If “Consortium” field is marked on the tender registration, “Co-tenders” function becomes available for the selected record. This function allows entering multiple vendors accounts, associated with one received tender if applicable (e.g. if more vendors together responded to the public procurement request).
 
 A new form opens where multiple vendor accounts from the register can be selected.
 
NOTE: all co-tenderers from which the invoices are expected to be received in relation to the Public procurement case outcome document (Purchase order, Purchase agreement or Framework agreement), should be entered, since only invoices from the specified vendors can be accepted in terms of the resulting document.  
1.1.1.2.	Subcontractors
Similarly to consortium, subcontractors can be added to each tender, by clicking “Subcontractors” button.
 
A new form opens, where vendors from the register can be specified as subcontractors.
 
In contrast to co-tenderers, Subcontractors serve only as additional information about the subcontractors involved with each tender, while no limitations in the further documents, related to the specified subcontractors exist.
1.1.1.3.	Copy vendors
When successfully selecting public procurement case parts (RFQ cases), tenderers should be transferred to these public procurement case parts (RFQ case), associated with each tender. This can be done by clicking “Copy vendors” function. Once completed, all the transferred lines are indicated with “Yes” mark in “Transferred” field of each tender.
When tenderers are transferred to adequate RFQ case, an informational message is also displayed.
 
 
Tenderers are transferred only to public procurement case parts (RFQ cases), marked with “In tender” checkmark, but only if Delivery status of their tenders is “In time” and the tenders are marked as “Properly labelled”:
 
1.1.1.4.	Send
Send functions performs same action, as “Send” function on the standard RFQ case form and is meant for sending RFQs to the specified vendors.
While standard D365O functionality requires RFQs to be sent to the specified vendors, in terms of public procurement procedures, RFQs are not actually sent to vendors from D365FO. »Send« action in terms of public procurement procedures is used only to reach the required status of the RFQ cases, which allows entering the tenderer replies.
For that purpose, make sure that »Purchaser can edit vendors bid« checkmark in Procurement and sourcing parameters is set to »Yes«. If this option is not enabled, only vendors to whom RFQs are sent can enter and modify their replies (e.g. actual quantities, prices, details) through Vendor collaboration procedures, which is not applicable in terms of public procurement procedures.
 
By clicking “Send” action, a new form opens, where users can specify to which of the connected RFQ case lines each of the tenderer responded:
 
By clicking “OK”, line status of the checkmarked lines on the associated RFQs changes to “Sent”, which is a prerequisite for entering tenderer replies later in the public procurement process.
 
An informational message is also displayed:
 
After refreshing the form, a new line appears in “Tenderer replies” section of the Public procurement case:
 
2.3.9	Tenderer replies
When RFQ case lines, associated with tenders, listed in the “Tender registration” section of the public procurement case are in status “Sent”, a separate line, associated with each of the registered tenders appears in the “Tenderer replies” section as seen on the screenshot above. By clicking on the “Request for quotation case” link on each line, or by selecting a specific line and clicking “Reply details”, RFQ connected with the tender opens and details about the tenderer replies can be entered.
 
 
Entering tenderer replies will not be described in details, since it is a standard D365O feature. 
Once replies have been managed (tenderer replies are submitted for each of the RFQ cases), status of each submitted tenderer reply on the associated public procurement case changes to “Received”. “Net amount” fields display the price, calculated based on the entered tenderer replies.
 
2.3.10	Public opening of tenders
In this section the location and time of the public opening of tenders can be specified by clicking »New« and typing in the location and opening Date and time.
 
2.3.11	Administration
This section displays information about the user who created the case and the creation date and time. Additionally, when case is closed, it also displays information about the closing user, date and time.
 
2.3.12	Legal protection events
Different legal protection event can also be entered if and when applicable by clicking “New”. Adequate fields then need to be filled in, depending on the legal event type:
-	Event type ID: selected from the register;
-	Applicant: worker who filed the request;
-	Date;
-	Application complete: (yes/no);
-	Commission decision: can be selected from the register;
-	Commission decision date;
-	…
Additionally, in the bottom part of the form, user can define to which of the RFQs a specific legal protection event refers to.
 
After legal protection event is completed, tender accepting process can begin.
2.4	Accept tenders
Before accepting the tenders, public procurement parts (RFQ cases connected with the public procurement case) should be marked as “Final”.
 
Information about the finality is also transferred to the RFQ case:
 
Tender replies can be compared by clicking “Accept tenders” button.
 
A new form opens, consisting of two additional tabs: (1) Request for quotation and (2) Acceptance of quotation.
(1)	RFQ cases associated with tenders to be accepted;
 
(2)	Based on the selected RFQ case in (1), tenderer replies are listed. User can select tenders to be accepted by adding a checkmark into “Marked” field:
 
NOTE: if a Purchase type of the public procurement case is “Framework agreement”, multiple vendors can be selected for one public procurement case part (RFQ case).
When the desired tenderer replies are selected, they can be accepted by clicking on the “Accept” button.
 
A new form for Accepting requests for quotation opens, where RFQ, tenderer’s name, and currency are displayed. Transaction date is automatically adjusted to the current system date, but can also be changed.
NOTE: a checkmark in the “Do not transfer inventory dimensions” field signifies that inventory dimensions from the RFQ case line, associated with the tender will not be transferred to the generated document (public procurement case result) and is applicable only if result of the public procurement case acceptance is either purchase agreement or framework agreement.
In the bottoms section of the form, RFQ case lines, associated with the tender replies to be accepted are displayed:
 
By clicking OK, another form for rejecting the remaining tenders opens. Section contains all the received tenderer replies, which have not been accepted in the previous step of the procedure:
 
When processing is completed, status of the accepted tenderer replies changes to “Accepted” and of those rejected to “Rejected”. This can be seen in:
(1)	 “Acceptance journal” section of the “Request for quotation acceptance” form or
 
(2)	Tenderer replies form, where the selected tender is also indicated:
 
Additionally, informational messages indicate the public procurement case processing results – created either Purchase order, Purchase agreement or Framework agreement.
 
2.4.1	Group acceptance journals
Additional parameter is added to procurement parameters that enables a grouping of accepted tenders by vendor account and currency code into a single document when the result of public procurement processing is a purchase agreement.
 
With the “Group acceptance journal” parameter enabled, if the result of the public procurement case acceptance is a purchase agreement, when the same vendor is marked as selected for different public procurement parts (different RFQs), a single output document is generated upon clicking Accept. The created purchase agreement contains all lines from accepted RFQs. 
 
2.5	Resulting document
Decision about the resulting document is defined by user at the point of Public procurement case creation, by selecting an adequate document in Purchase type field. This process is described in chapter 2.2.
 
NOTE: in case of a chosen tender from a tenderer consortium, multiple documents (purchase agreements) are created because of public procurement case – one for each of the specified co-tenderers and one for vendor, which defines the vendor consortium.
 
   
2.5.1	Purchase order
If a result of a public procurement case is purchase order, purchase type “Purchase order” has been defined when generating the case. If any other document had been selected upon the public procurement case creation, these documents would be created instead.
 
It can be accessed through standard D365O forms for accessing purchase orders. All the information (header and line details) about the tenders are transferred from the related tender (RFQ case part associated with the tender) to this newly created purchase order (standard D3565O functionality). Purchase order is created in status “Approved”.
 
2.5.2	Purchase agreement
If Purchase agreements are created because of a public procurement case, they can be accessed through standard D365O forms for accessing purchase agreements. Header and line information about the accepted tender are transferred from the related RFQ case parts, included in the accepted tender.
 
 
If tender from a consortium of tenderers have been accepted in public procurement case, then one purchase agreement is created for each of the involved vendor accounts in D365O:
 
Information about the related purchase agreements, resulting from the accepted tender for a consortium of tenderers can be seen in “Related agreements” section on each of the related agreements.
    
2.5.3	Framework agreement
If purchase type “Framework agreement” has been defined when generating the public procurement case, result of the case process is a generated framework agreement. One framework agreement can consist out of multiple case parts and tenders related to each of these parts (RFQ cases).
 
NOTE: Purchase type “Framework agreement” is displayed as an option also when creating RFQ cases, but cannot be manually selected there.
 
Prior to generating framework agreements, number sequences used for Framework agreements need to be configured in Organizational administration module, with the following settings:
-	Scope: »Shared”;
-	Area: “Purchase” and
-	Reference: “Framework agreement ID”.
 
After tenders are accepted, Framework agreement is created based on the pre-set number sequence. 
 
2.6	Send decisions
Notifying tenderers about the acceptance or rejection of their tenders can be recorded on the Public procurement case in the “Tender registrations” section. By selecting an adequate tenderer, “Decision sending date” and “Decision delivery” date can be entered. 
 
This procedure should be repeated for each tenderer, included on the public procurement case.
NOTE: publishing decision about the accepted/rejected tenders can only indicated in D365O, while it may have to be manually updated on the adequate public procurement portal.
2.7	Close case
Once public procurement process is complete, case can be marked as “Closed”. This can be done by clicking “Change status” and selecting “Closed”.
 
In the “Administration” section, “Closed by” fields display the name of the user, who closed the case, along with the closed date and time.
 
3.	Framework agreements
3.1	Form description
Procurement and sourcing/Purchase agreements/Framework agreements
Creation of Framework agreements is discussed throughout chapter Framework agreement. Once created, Framework agreements list displays all the generated framework agreements:

 
Information in section General is transferred directly from the public procurement case, from which framework agreement has been created (indicated in “Case ID” field).
Selected parts and vendors section displays all the accepted tenders from the originating public procurement case. 
 
Lines section displays information about the lines, from the accepted tenders, while in Line details section more information about each of the lines is displayed throughout multiple tabs, as described in the following paragraphs.
GENERAL tab displays information about the:
-	Agreement line product (Procurement category or Item) and procurement category/item name;
-	Agreement ID (ID of the framework agreement to which each line belongs to);
-	Part (public procurement case part – the originating RFQ case) and
-	Project ID (if the referring RFQ line is linked to a project).

 
PRICE AND DISCOUNT displays information about the Quantity, Price, Units, Amounts and Currency.
FULFILLMENT section displays the:
-	Remaining (total remaining amount, left to be released in terms of framework agreement line);
-	Released to request for quotations;
-	Released to purchase agreements;
-	Released to request purchase orders.
 
Releasing from framework agreements can be done by linking the RFQ case directly with the framework agreement and connecting them with a public procurement case, as described throughout the following chapter.
3.2	Releasing from framework agreement
A public procurement case, which refers to a framework agreement, is created through creating RFQ cases. Firstly, an adequate framework agreement needs to be selected in the RFQ case header section, and then adequate RFQ case(s) need to be connected to a public procurement case.
NOTE: only RFQ cases associated with the same framework agreement can be connected to the same public procurement case.
Framework agreements can be selected directly on each RFQ case by clicking “Select framework agreement” button:
 
A new form opens where it is possible to select applicable framework agreement to be associated with the RFQ case (“Framework agreement parts” section) and mark lines from the agreement, which will be released throughout the RFQ case. If one framework agreement consists of multiple parts (tenders), separate records on the list display all the existing framework agreement and part combinations:
 
NOTE: only framework agreements in Status “Effective” are displayed on the list.
In “Actions” section, connection between the lines from the RFQ and framework agreement are defined:
 
Actions work in the following way:
(1)	If none of the (two) checkmarks is checked, no connection will be created between the framework agreement and RFQ case – only headers of both document will be connected. In case of framework agreement with multiple parts, only parts on which we are positioned before clicking “Ok” will be connected.
(2)	If “Automatically match existing lines” is checked, a new connection between the existing framework agreement and RFQ case lines will be created:
o	In case of Procurement categories: if same Procurement category is selected on both – framework agreement and RFQ case line or a procurement category, subordinate to the one from the framework agreement is selected on the RFQ case line;
o	In case of Items:
	If same Item is specified on framework agreement and RFQ case line;
	If Item from the RFQ case, line is connected with the procurement category on the framework agreement or is connected to its subordinate procurement category.
NOTE: manually connecting lines, described in the following part of this section uses the same principle for connecting the framework agreement and RFQ case lines as described above.
(3)	If “Create lines from selection” is checked, lines on the RFQ case are created based on the selected lines from the framework agreement (selected before clicking “Ok”). Subsequently a connection between the newly generated RFQ case lines and framework agreement lines will be automatically created.
 
 
If connecting framework agreement to RFQ case prior to entering RFQ case lines, these lines need to be manually connected with an adequate framework agreement part. This can be done by clicking on “Update line” and “Create link”:
 
A new form opens with lines from the selected framework agreement part, which match with the procurement category or item from the RFQ case line:
 
Same rules for matching the framework agreement and RFQ lines, as described above when describing the “Release from framework agreement” actions apply if lines are connected manually.
A link between the RFQ and framework agreement can also be removed – on both header and line level:
 
Attached (connected) framework agreement lines, connected with each line of the RFQ can also be viewed:
 
 
A new public procurement case can then be created directly from the RFQ case. This newly generated public procurement case is automatically connected with the framework agreement (or its part), connected with the originating RFQ case. All lines from the RFQ cases, connected with the same public procurement case need to be connected to a framework agreement. If connecting multiple RFQ cases to the same public procurement case, lines from all these RFQs need to be connected to the same framework agreement.
 
Trying to add RFQ cases, connected with different framework agreements to one public procurement case will result in an error:
 
When RFQ(s), connected with a framework agreement are added to a public procurement case, framework agreement is displayed in the Agreement ID field on the case:
 
In the “Proposed vendors” section of the public procurement case, vendors from each part (RFQ case) of the connected framework agreement are displayed:
 
When registering tenders, connected with the public procurement case, only vendors from the “Proposed vendors” section can be registered as tenderers:
 
The rest of the public procurement procedure is same as for any other public procurement cases and is described throughout previous sections of this document.
When tenders are accepted, fulfilment of the referring lines from the framework agreement is updated, according to the Purchase type from the public procurement case:
 
 
 
 

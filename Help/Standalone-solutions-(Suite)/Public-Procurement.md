# Public Procurement

Public procurement is a set of actions, with the objective of purchasing goods, services or contractual works in a more economical way. In some countries, the use of prescribed public procurement procedures is often mandatory, especially for direct or indirect users of national and local budgets. Regardless of the type and extent of the order, these entities must respect the fundamental principles of public procurement, such as the economic use of public funds, the equity of providers, the transparency of the procedures, and the principle of ensuring competition between the tenderers. All public procurement contracts have to be in accordance with these principles, therefore this functionality enhances and adds to the standard D365O functionality for the purpose of simple, efficient and legally correct public procurement.

Throughout the following sections of this document, functionalities and forms connected with different public procurement procedures will be presented, together with their embeddedness with the standard D365O features, required for public procurement processes. The main purpose of this document, therefore, is to present how public procurement is performed in D365O.

Firstly, the required setup in terms of public procurement is described, followed by the overview of public procurement procedures and the role of additionally developed functionalities (Public procurement case enhancements and Framework agreements) in these procedures. Additionally, enhancements added to standard D365O forms (e.g. purchase orders or requests for quotation) are presented throughout the document.

## Public procurement parts


Public procurement parts refer to requests for quotation (RFQ) cases, which are used as input documents to successfully perform public procurement procedures. Throughout the following chapter, required setup, prerequisites, and additionally developed functionalities, required for an adequate RFQs creation for the purpose of public procurement procedures are presented.

### Request for quotation case enhancements

RFQ cases are used as inputs (parts) of public procurement cases, described in the following chapter (2). Although RFQ cases are standard D365O functionality, some additional enhancements are added for the purpose of public procurement procedures. These enhancements are described throughout the following paragraphs.
Public procurement functionality adds the “Public procurement” section in the RFQ case header. This section contains »Case ID« and »Description« fields, which are populated with the public procurement case ID and description once the RFQ case is connected with the procurement case. Additionally, information in the »Expected date of finality« and »Final« checkmark display information about the connected case finality:
 
Once created, RFQ cases can be added to either a new or an existing public procedure case, using the “Create case” or “Add to case” actions: 
 
If RFQ case is to be connected to a public procurement case, its purchase type should be either “Purchase order” or “Purchase agreement”, depending on the desired document, created because of the related public procurement case.
 
For the purpose of public procurement procedures in D365O, RFQ cases should only contain lines with the ordering goods/services. Proposed vendors should not be defined directly on each RFQ case, but directly on public procurement case, which is described later throughout this document (chapter 2.4.8). 
All other processes (e.g. sending RFQs or entering vendor replies to RFQ cases) are also performed directly from the public procurement case and are not supposed to be performed through RFQ case form.

## Public procurement cases

Public procurement cases functionality is used to perform public procurement procedures in D365O.

### Setup

#### Case categories

Case categories are used to distinguish between different public procurement procedures. The required number of case categories, therefore, depends on the types of distinct public procurement processes required to be performed in D365O. For each public procurement procedure (e.g. Low-value order or Open procedure), a unique case category is proposed to be created.

1. Open Organization administration - Setup - Cases - Case categories.
2. New Case categories can be created by clicking »New«, then enter a name and description to an adequate hierarchy node. For each case category, a default case process can be set. Case processes specify the steps for each distinct public procurement process and are further described throughout the following chapter (2.1.2).
3. In the “Public procurement amount limits” section, order value for each public procurement case category can be set. Amounts refer to the total amount of the combined public procurement case parts (RFQ cases), added to the case. However, no amount of validation exists, while these amounts are mainly informational.
 
If the total amount of the combined RFQ cases connected with the public procurement case is lower or exceeds the defined amount limits, the “Amount status” field in the “General” section of the public procurement case displays information about the low or exceeded limit.
 
Additionally, amount limits are checked, if “Propose case categories” function is used when adding RFQ cases to a new public procurement case.
 
#### Case processes

The case process is a predefined template, which describes the expected steps in the process of each of the public procurement cases. Case processes can be defined per case category or separately for each public procurement case.
A new case process can be created by clicking “New” and adding responsibilities – a list of all the possible stages within the process.

1. Open Organization administration - Setup - Cases - Case processes.
2. Once Responsibilities are entered, process hierarchy can be defined. This is done by clicking the “Details” button under the “Process” tab.
3. The hierarchy of the entered process steps can be added by clicking “New” - “Level”. A new form opens, where additional information about each of the steps in the process can be entered.
 
#### Case Statuses and Stages

When newly created, the public procurement case is in status “Opened”. When users start working with the case, status can be updated to “In process” by clicking the “Change status” button.
 
Additionally, public procurement case stages indicate which part of the public procurement procedure the case currently is. These stages serve only as information for the case users. Thus, no validation connected with each of the case stages exists. The setup of the public procurement case stages is described in the chapter above.
 
Each stage of the case can be started by clicking the »Change stage« and selecting the applicable stage. For example, the »Public procurement members« stage should proceed once, the adequate members have been added to the Public procurement case.
 
NOTE: both – Public procurement case statuses and stages only have the informational value for users - e.g. to get an insight into a stage of the public procurement or easily filter out the desired public procurement cases. However, no validation linked with either specific public procurement case status or stage exists.

### Create case

1. Public procurement cases can be created:
   - Directly from the RFQ case: On RFQ case click on either “Create case” (creates a new public procurement case) or “Add to case” (connects RFQ case with an already existing public procurement case) button.
   - Through Public procurement cases form: Procurement and sourcing - Public procurement cases - All cases
Click on “New” - “Case”.
2. Following any of the above-described procedures (1 or 2), a new form opens. If action to add RFQ case to an already existing case is selected, a new form opens, where users can select the public procurement case, with which they want to connect the RFQ case.
3. If an action to create a new public procurement case out of the RFQ case is selected, a different form opens, where it is possible to determine additional information about the public procurement case. This information is described below by each section of the public procurement case form: 
   - GENERAL:
      - Name: selected from the workers and contractors register (used to ease the filtering of cases);
      - Case category: select an adequate public procurement case category from the register;
      - Case ID: generated automatically according to the number sequences setup;
      - Description: description (content) of the public procurement case can be added;
      - Priority: can be selected from the register;
      - Parent case: an existent public procurement case can be selected if applicable;
      - Status: can be selected from the register.
    - PUBLIC PROCUREMENT:
      - Purchase type: the desired result of the public procurement case (Purchase agreement, Purchase order or Framework agreement);
      - Solicitation type: selected from the register (Constructions, Goods or Services);
      - Expiry date and time: expiry date of the Public procurement case (final date for the acceptance of vendor quotations);
      - Subject: a free text field (e.g. longer description of the public procurement case);
      - Agreement ID: link to an associated Framework agreement if it exists.
    - OTHER: 
      - Department: the department responsible for the public procurement case;
      - Employee responsible: an employee responsible for the public procurement case (selected from the employee's register);
      - Case process: populated automatically according to case category (defined in “General” section) – it can still be changed by selecting an adequate value from the register.

After all the required information for a specific public procurement case is entered, the case can be created by clicking the »Create« button in the bottom right corner of the form. A public procurement case form opens, where most of the information, entered upon creating the case can still be edited. The public procurement case form and its processing is described throughout the following chapter.

### Case sections

Throughout the following part of the document, sections of the Public procurement case form, together with their purpose and functionalities are described.

#### General

A general section consists of mostly the information, which can already be entered upon creating a new public procurement case (as described in chapter *Create Case*). Additionally, a Primary contact connected with the case can be selected from the contacts register.
 
#### Public procurement parts

This section consists of the RFQ cases, related to the public procurement case. If public procurement case has been created directly from the RFQ case (as described in chapter *Create Case*, RFQ number from which public procurement case has been created is automatically displayed in the public procurement parts sections. On the other hand, if public procurement case has been created throughout the Public procurement cases form (as described in chapter *Create Case*), RFQ case(s), which the user wants to associate with the public procurement case need to be manually added. This can be done by clicking on the »New« button. Details about each of the related RFQ cases can be viewed by clicking on the »Details« button, which opens the selected RFQ case. By clicking the “Delete” button, RFQ case(s) can also be removed from the public procurement case.
 
The ID of the connected RFQ case(s), their Title and Net amount are automatically transferred from each RFQ case when they are added to the public procurement case.

Additionally, Expected dates of finality and a checkmark whether quotations in relation to each RFQ are Final can be specified. Their function is described later throughout the document.

#### Public procurement members

In this section, it is possible to add members (e.g. of the Expert commission), related to the public procurement case. 
1. This can be done by clicking »New« and selecting adequate member roles (from the register of roles), then assigning each role to a worker (from the register of workers). 
2. For each of the selected members, a Description and duration of their membership in the public procurement case can be defined. 
3. Multiple members can be added (as separate lines).
 
#### Public procurement attachments

Attachments can also be added to the Public procurement case. 

1. This can be done by clicking »New« and selecting the present attachment type from the register. 
2. Once a new line is created, desired files to be attached (e.g. service/goods specifications, different documentation) can be added to each line, by clicking the »Attachments« button.
3. A new (standard) form opens where a file type can be selected, uploaded  and other details about the attached file can be filled in. 
 
#### Public procurement identifications

Once a public procurement case is officially published on an adequate public procurement portal, Public procurement identifications (št. Javnega naročila) can be entered.
  
#### Certifications

Additional enhancement on certifications is added as part of public procurement functionality, and that is the Certification insurance type. Upon certification entry on vendor form, the field Certification insurance type is added to the standard form to ensure the additional classification of vendor certificates. 
 
1. The values for drop-down selection in this field are entered in the code list at Procurement and sourcing - Setup - Vendors - Certification insurance type.
2. If certifications are applicable for an individual public procurement case, they can be added in this section by clicking “New”, specifying Vendor (it is possible to choose from all the tenderers, co-tenderers or subcontractors specified in “Tenderer registration section” of the public procurement case) and selecting Certification type from the related register.
3. One vendor certificate can only be used for one public procurement case. It is not possible to use the same certificate on multiple cases.

#### Proposed vendors

The proposed vendors section is used only for public procurement procedures, connected with a Framework Agreement. If a Framework agreement is linked to a Public procurement case, the Proposed vendors section displays vendors (tenderers) from the related agreement. If public procurement is not linked to a Framework agreement, proposed vendors should not be entered.
 
#### Tender registration

1. Tender registrations section serves for registering tenders, who responded to the specific public procurement request. The following fields are available to be entered for each tender (line):
   - Date and time: of the received tender;
   - Vendor’s account: vendor’s account from the vendor’s register (NOTE: if vendors are added to “Proposed vendors” section of the public procurement case, only these specified vendors can be selected when registering tenderers);
   - Consortium: should be checked if the line refers to the consortium of vendors;
   - Worker: who registered the tender is automatically selected from the register upon entering each new tender;
   - Delivery status: indicates whether tender has been received within the specified public procurement case Expiry date - “Late” or “In time” options are available (NOTE: only tenders from the tenderers who sent their tenders “In time” can be accepted later in the process);
   - Submission method: indicates the method by which tenderer has submitted the tender (e.g. by mail or electronically);
   - Delivered by: a free text field (e.g. name of the delivery person); 
   - Properly labeled: indicates whether the received tender is properly labeled (NOTE: only properly labeled tenders can be accepted later in the process);
   - Number of consignments: indicates the number of the received consignments connected with the tender.
2. In the bottom part of the form, users can specify to which RFQ case from the “Public procurement parts” each tender reefers to. The bottom part of the form consists of as many lines as there are RFQ cases (public procurement parts) related to the public procurement case.

For example – tender from “Telekom Slovenije, d.d.” refers to the goods/services from the public procurement part “000076”. This is indicated with the “In tender” checkmark:
 
##### Consortium

1. If the “Consortium” field is marked on the tender registration, the “Co-tenders” function becomes available for the selected record. This function allows entering multiple vendors accounts, associated with one received tender if applicable (e.g. if more vendors together responded to the public procurement request).
2. A new form opens where multiple vendor accounts from the register can be selected.
 
NOTE: all co-tenderers from which the invoices are expected to be received in relation to the Public procurement case outcome document (Purchase order, Purchase agreement or Framework agreement), should be entered since only invoices from the specified vendors can be accepted in terms of the resulting document.  

##### Subcontractors

1. Similarly to a consortium, subcontractors can be added to each tender, by clicking the “Subcontractors” button.
2. A new form opens, where vendors from the register can be specified as subcontractors.
 
In contrast to co-tenderers, Subcontractors serve only as additional information about the subcontractors involved with each tender, while no limitations in the further documents, related to the specified subcontractors exist.

##### Copy vendors

1. When successfully selecting public procurement case parts (RFQ cases), tenderers should be transferred to these public procurement case parts (RFQ case), associated with each tender. This can be done by clicking the “Copy vendors” function. Once completed, all the transferred lines are indicated with the “Yes” mark in the “Transferred” field of each tender.
2. When tenderers are transferred to an adequate RFQ case, an informational message is also displayed.
3. Tenderers are transferred only to public procurement case parts (RFQ cases), marked with “In tender” checkmark, but only if the Delivery status of their tenders is “In time” and the tenders are marked as “Properly labeled”:
 
##### Send

Send functions performs the same action, as the “Send” function on the standard RFQ case form and are meant for sending RFQs to the specified vendors.

While standard D365O functionality requires RFQs to be sent to the specified vendors, in terms of public procurement procedures, RFQs are not actually sent to vendors from D365FO. »Send« action in terms of public procurement procedures is used only to reach the required status of the RFQ cases, which allows entering the tenderer replies.

For that purpose, make sure that »Purchaser can edit vendors bid« checkmark in Procurement and sourcing parameters is set to »Yes«. If this option is not enabled, only vendors to whom RFQs are sent can enter and modify their replies (e.g. actual quantities, prices, details) through Vendor collaboration procedures, which is not applicable in terms of public procurement procedures.
 
1. By clicking “Send” action, a new form opens, where users can specify to which of the connected RFQ case lines each of the tenderers responded:
2. By clicking “OK”, line status of the marked lines on the associated RFQs changes to “Sent”, which is a prerequisite for entering tenderer replies later in the public procurement process.
 
An informational message is also displayed.
 
3. After refreshing the form, a new line appears in the “Tenderer replies” section of the Public procurement case.
 
#### Tenderer replies

When RFQ case lines, associated with tenders, listed in the “Tender registration” section of the public procurement case are in status “Sent”, a separate line, associated with each of the registered tenders appears in the “Tenderer replies” section as seen on the screenshot above. 

1. By clicking on the “Request for quotation case” link on each line, or by selecting a specific line and clicking “Reply details”, RFQ connected with the tender opens and details about the tenderer replies can be entered.
2. Entering tenderer replies will not be described in detail since it is a standard D365O feature. 
3. Once replies have been managed (tenderer replies are submitted for each of the RFQ cases), the status of each submitted tenderer reply on the associated public procurement case changes to “Received”. “Net Amount” fields display the price, calculated based on the entered tenderer replies.
 
#### Public opening of tenders

In this section, the location and time of the public opening of tenders can be specified by clicking »New« and typing in the location and opening date and time.
 
#### Administration

This section displays information about the user who created the case and the creation date and time. Additionally, when the case is closed, it also displays information about the closing user, date and time.
 
#### Legal protection events

1. Different legal protection event can also be entered if and when applicable by clicking “New”. Adequate fields then need to be filled in, depending on the legal event type:
   - Event type ID: selected from the register;
   - Applicant: a worker who filed the request;
   - Date;
   - Application complete: (yes/no);
   - Commission decision: can be selected from the register;
   - Commission decision date.
2. Additionally, in the bottom part of the form, the user can define which of the RFQs a specific legal protection event refers to.
3. After the legal protection event is completed, a tender accepting process can begin.

### Accept tenders

1. Before accepting the tenders, public procurement parts (RFQ cases connected with the public procurement case) should be marked as “Final”. Information about the finality is also transferred to the RFQ case.
2. Tender replies can be compared by clicking the “Accept tenders” button.
3. A new form opens, consisting of two additional tabs: (1) Request for quotation and (2) Acceptance of quotation.
   - RFQ cases associated with tenders to be accepted;
   - Based on the selected RFQ case in (1), tenderer replies are listed. Users can select tenders to be accepted by adding a checkmark into the “Marked” field.
 
NOTE: if a Purchase type of the public procurement case is “Framework agreement”, multiple vendors can be selected for one public procurement case part (RFQ case).
When the desired tenderer replies are selected, they can be accepted by clicking on the “Accept” button.
 
4. A new form for Accepting requests for quotation opens, where RFQ, tenderer’s name, and currency are displayed. Transaction date is automatically adjusted to the current system date, but can also be changed.

NOTE: a checkmark in the “Do not transfer inventory dimensions” field signifies that inventory dimensions from the RFQ case line, associated with the tender will not be transferred to the generated document (public procurement case result) and is applicable only if result of the public procurement case acceptance is either purchase agreement or framework agreement.

5. In the bottoms section of the form, RFQ case lines, associated with the tender replies to be accepted are displayed.
6. By clicking OK, another form for rejecting the remaining tenders opens. The section contains all the received tenderer replies, which have not been accepted in the previous step of the procedure.
7. When processing is completed, the status of the accepted tenderer replies changes to “Accepted” and of those rejected to “Rejected”. This can be seen in:
   - “Acceptance journal” section of the “Request for quotation acceptance” form or
   - Tenderer replies form, where the selected tender is also indicated.
8. Additionally, informational messages indicate the public procurement case processing results – created either Purchase order, Purchase agreement or Framework agreement.
 
#### Group acceptance journals

An additional parameter is added to procurement parameters that enable a grouping of accepted tenders by vendor account and currency code into a single document when the result of public procurement processing is a purchase agreement.
 
With the “Group acceptance journal” parameter enabled, if the result of the public procurement case acceptance is a purchase agreement when the same vendor is marked as selected for different public procurement parts (different RFQs), a single output document is generated upon clicking Accept. The created purchase agreement contains all lines from accepted RFQs. 
 
### Resulting document

A decision about the resulting document is defined by the user at the point of Public procurement case creation, by selecting an adequate document in the Purchase type field. This process is described in chapter *Create Case*.
 
NOTE: in case of a chosen tender from a tenderer consortium, multiple documents (purchase agreements) are created because of public procurement case – one for each of the specified co-tenderers and one for a vendor, which defines the vendor consortium. 
   
#### Purchase order

If a result of a public procurement case is a purchase order, purchase type “Purchase order” has been defined when generating the case. If any other document had been selected upon the public procurement case creation, these documents would be created instead.
 
1. It can be accessed through standard D365O forms for accessing purchase orders. 
2. All the information (header and line details) about the tenders are transferred from the related tender (RFQ case part associated with the tender) to this newly created purchase order (standard D3565O functionality). 
3. A purchase order is created in status “Approved”.
 
#### Purchase agreement

If Purchase agreements are created because of a public procurement case, they can be accessed through standard D365O forms for accessing purchase agreements. Header and line information about the accepted tender are transferred from the related RFQ case parts, included in the accepted tender.
 
1. If tender from a consortium of tenderers has been accepted in public procurement case, then one purchase agreement is created for each of the involved vendor accounts in D365O:
2. Information about the related purchase agreements, resulting from the accepted tender for a consortium of tenderers can be seen in the “Related agreements” section on each of the related agreements.
    
#### Framework agreement

1. If the purchase type “Framework agreement” has been defined when generating the public procurement case, a result of the case process is a generated framework agreement. One framework agreement can consist out of multiple case parts and tenders related to each of these parts (RFQ cases).
 
NOTE: Purchase type “Framework agreement” is displayed as an option also when creating RFQ cases, but cannot be manually selected there.
 
2. Prior to generating framework agreements, number sequences used for Framework agreements need to be configured in Organizational administration module, with the following settings:
   - Scope: »Shared”;
   - Area: “Purchase” and
   - Reference: “Framework agreement ID”.
3. After tenders are accepted, a Framework agreement is created based on the pre-set number sequence. 
 
### Send decisions

1. Notifying tenderers about the acceptance or rejection of their tenders can be recorded on the Public procurement case in the “Tender registrations” section. By selecting an adequate tenderer, “Decision sending date” and “Decision delivery” date can be entered. 
2. This procedure should be repeated for each tenderer, included in the public procurement case.

NOTE: publishing decision about the accepted/rejected tenders can only be indicated in D365O, while it may have to be manually updated on the adequate public procurement portal.

### Close case

1. Once the public procurement process is complete, the case can be marked as “Closed”. This can be done by clicking “Change status” and selecting “Closed”.
2. In the “Administration” section, “Closed by” fields display the name of the user, who closed the case, along with the closed date and time.
 
## Framework agreements

### Form description

1. Open Procurement and sourcing - Purchase agreements - Framework agreements.
2. The creation of Framework agreements is discussed throughout the chapter Framework agreement. Once created, the Framework agreements list displays all the generated framework agreements:
3. Information in section General is transferred directly from the public procurement case, from which framework agreement has been created (indicated in the “Case ID” field).
Selected parts and vendors section displays all the accepted tenders from the originating public procurement case. 
4. Lines section displays information about the lines, from the accepted tenders, while in Line details section more information about each of the lines is displayed throughout multiple tabs, as described in the following paragraphs.
   - GENERAL tab displays information about the:
     - Agreement line product (Procurement category or Item) and procurement category/item name;
     - Agreement ID (ID of the framework agreement to which each line belongs to);
     - Part (public procurement case part – the originating RFQ case) and
     - Project ID (if the referring RFQ line is linked to a project).
   - PRICE AND DISCOUNT display information about Quantity, Price, Units, Amounts, and Currency.
   - FULFILLMENT section displays the:
     - Remaining (total remaining amount, left to be released in terms of framework agreement line);
     - Released to request for quotations;
     - Released to purchase agreements;
     - Released to request purchase orders.
5. Releasing from framework agreements can be done by linking the RFQ case directly with the framework agreement and connecting them with a public procurement case, as described throughout the following chapter.

### Releasing from a framework agreement

1. A public procurement case, which refers to a framework agreement, is created by creating RFQ cases. Firstly, an adequate framework agreement needs to be selected in the RFQ case header section, and then adequate RFQ case(s) need to be connected to a public procurement case.

NOTE: only RFQ cases associated with the same framework agreement can be connected to the same public procurement case.
2. Framework agreements can be selected directly on each RFQ case by clicking “Select framework agreement” button:
3. A new form opens where it is possible to select applicable framework agreement to be associated with the RFQ case (“Framework agreement parts” section) and mark lines from the agreement, which will be released throughout the RFQ case. If one framework agreement consists of multiple parts (tenders), separate records on the list display all the existing framework agreements and part combinations.
 
NOTE: only framework agreements in Status “Effective” are displayed on the list.
In the “Actions” section, a connection between the lines from the RFQ and framework agreement are defined:
 
4. Actions work in the following way:
   - If none of the (two) checkmarks are checked, no connection will be created between the framework agreement and RFQ case – only headers of both documents will be connected. In the case of a framework agreement with multiple parts, only parts on which we are positioned before clicking “Ok” will be connected.
   - If “Automatically match existing lines” is checked, a new connection between the existing framework agreement and RFQ case lines will be created:
     - In case of Procurement categories: if same Procurement category is selected on both – framework agreement and RFQ case line or a procurement category, subordinate to the one from the framework agreement is selected on the RFQ case line;
     - In the case of Items:
       - If the same Item is specified on the framework agreement and RFQ case line;
       - If Item from the RFQ case, a line is connected with the procurement category on the framework agreement or is connected to its subordinate procurement category.
NOTE: manually connecting lines, described in the following part of this section uses the same principle for connecting the framework agreement and RFQ case lines as described above.
   - If “Create lines from selection” is checked, lines on the RFQ case are created based on the selected lines from the framework agreement (selected before clicking “Ok”). Subsequently, a connection between the newly generated RFQ case lines and framework agreement lines will be automatically created.
5. If connecting framework agreement to RFQ case prior to entering RFQ case lines, these lines need to be manually connected with an adequate framework agreement part. This can be done by clicking on the “Update line” and “Create link”.
6. A new form opens with lines from the selected framework agreement part, which match with the procurement category or item from the RFQ case line.
8. The same rules for matching the framework agreement and RFQ lines, as described above when describing the “Release from framework agreement” actions apply if lines are connected manually.
9. A link between the RFQ and framework agreement can also be removed – on both the header and the line level.
10. Attached (connected) framework agreement lines, connected with each line of the RFQ can also be viewed.
11. A new public procurement case can then be created directly from the RFQ case. This newly generated public procurement case is automatically connected with the framework agreement (or its part), connected with the originating RFQ case. All lines from the RFQ cases, connected with the same public procurement case need to be connected to a framework agreement. If connecting multiple RFQ cases to the same public procurement case, lines from all these RFQs need to be connected to the same framework agreement.
12. Trying to add RFQ cases, connected with different framework agreements to one public procurement case will result in an error.
13. When RFQ(s), connected with a framework agreement is added to a public procurement case, the framework agreement is displayed in the Agreement ID field on the case.
14. In the “Proposed vendors” section of the public procurement case, vendors from each part (RFQ case) of the connected framework agreement are displayed.
15. When registering tenders, connected with the public procurement case, only vendors from the “Proposed vendors” section can be registered as tenderers.
 
The rest of the public procurement procedure is the same as for any other public procurement cases and is described throughout previous sections of this document.

16. When tenders are accepted, the fulfilment of the referring lines from the framework agreement is updated, according to the Purchase type from the public procurement case.
 
 
 
 

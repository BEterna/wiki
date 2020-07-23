Classification of purchase documents functionality offers the ability to tag procurement documents with user defined values for the purposes of reporting. Code list for tag types enables the user to define any number of tag types for which corresponding tag values should be specified. Tags, added to purchase documents, serve as an additional classification in the business process, and transfer from one document to another, following the processing logic. 

# **Setup**
---

### **Tag type and value**

1. Go to **Procurement and sourcing > Setup > Classification of purchase documents > Tag type and value**
2. In the Tag type field, **create tag types** by entering tag type name, unique reporting value and order. Under each tag type create as many tag values as needed with reporting value and order priority. 

|Field|Description  |
|--|--|
|**Reporting value**  |identifier of tag type or tag value that is displayed on documents; max 5 characters allowed.  |
|**Order**  |specify the priority order in which the combination values are displayed on documents. Each tag type should have different order priority, each tag value for tag type should have different order priority.   |

3. Once a combination of tags is added to a purchase document, a **tag value combination** is created in the background. Neither tag type nor tag value can be deleted from the code list if they have already been used on a purchase document. 


### **Transfer setup**

1. Go to **Procurement and sourcing >Setup > Procurement and sourcing parameters > tab General > field Tag transfer control** 
2. Define the **options for tag transfers** between purchase documents when multiple documents with different tags are merged to one document:
   - If **parameter is set to Yes**: the union of tags is transferred to the new document, without the same values being repeated.
   - If **parameter is set to No**: no union of tags; tags do not transfer where multiple values would be created for one tag type; the user selects the value(s) for that tag type manually. 


# **Procurement tags usage**
---

## **Manage tags on purchase documents**

Purchase documents that facilitate tags:
- Purchase requisition (PR)
- Purchase order (PO)
- Purchase agreement (PA)
- Request for quotation (RFQ)
- Public procurement case (PPC) 
- Framework agreement (FA) 

Tags can be added to purchase documents using button **Manage tags** in the Action pane. New dialog window opens where Tag value can be selected for each added Tag type.

Once saved, the tag values for each type are displayed in the **Tag combination value field** in the document detail header, using reporting values. Separator between tag types is pipe sign: |.

**Tag combination value column** is added to the list pages of the following purchase documents: Purchase requisition, Purchase order, Purchase agreement, Request for quotation, and Public procurement case. The information about Tag combination value is available for filtering.

### **Framework agreement**

_**Note**: Tags can also be used in connection with Public procurement package. Following option is available only if Public procurement package is installed._

**Tag combination value field** is available on form detail and displays a value from the related public procurement case (there is no option to manage tags for FA document). Tag combination value column is not displayed in the list page of Frameworks agreements. 

## **Transfer of tags between documents**

Tags are transferred from existing document(s) to a new one upon document creation. If one purchase document that contains tags is used to create another (1:1 relation), all tags are transferred to a newly created document. If the relation is n:1 (multiple documents are combined to create a new document), transfer of tags follows the selected option in the procurement setup from chapter Transfer setup (union of tags or no union).

Possible **scenarios** of tag transfer between purchase documents (PR=Purchase requisition; PO=Purchase order; RFQ=Request for quote; PA=Purchase agreement; PPC=Public procurement case; FA=Fixed asset):
- PR > PO (1:1) – transfer of all tags
- PR > PO (n:1) – transfer should follow the selected option in the procurement setup
- PR > RFQ (1:1) – transfer of all tags
- PR > RFQ (n:1) – transfer should follow the selected option in the procurement setup
- RFQ > PR – update of tags from RFQ to PRs for accepted bids
- RFQ > PO – transfer of all tags
- RFQ > PA – transfer of all tags
- PA > PO – transfer of all tags
- RFQ > PPC (1:1) – transfer of all tags
- RFQ > PPC (n:1) – transfer should follow the selected option in the procurement setup
- PPC > PO – transfer of all tags
- PPC > PA – transfer of all tags
- PPC > FA – transfer of all tags
- FA > (RFQ > PPC >) PA – transfer of all tags
- FA > (RFQ > PPC >) PO – transfer of all tags

**Changing the tags** on documents after a new document has already been created from them does not reflect on already created document. Changing the tag values on the documents after they have been approved in the **workflow**, does not require the documents to go through workflow again.

## **Availability of tags in workflow configurations**

Tag combination value is available in **Purchase order** and **Purchase requisition workflow configuration**. 

## **Availability of tags in data entities**

There are **two new data entities** for importing and/or exporting code list Tag type and value:
- Purchase documents tag types
- Purchase documents tag value

Tag types are also available through **Open in Excel** functionality in Tag type and value code list.

The following **data entities** for purchase documents are extended with TAGVALUECOMBINATION DISPLAYVALUE field:
- Purchase requisitions V2 (PurchaseRequisitionHeaderV2Entity.AdPE) 
- Purchase agreements V2 (PurchaseAgreementHeaderV2Entity.AdPE) 
- Purchase order headers V2 (PurchaseOrderHeaderV2Entity.AdPE) 
- Case detail (CaseDetailBaseEntity.AdPE)****

The information about Tag value combination display value is available **only for data export**. Tag value combination cannot be imported using data entities or through Open in Excel functionality (the field is non-editable).

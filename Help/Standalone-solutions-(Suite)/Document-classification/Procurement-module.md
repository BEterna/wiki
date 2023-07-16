#Tags on Procurement documents 
---

The following purchase documents facilitate tags functionality:
- Purchase requisition (PR)
- Purchase order (PO)
- Purchase agreement (PA)
- Request for quotation (RFQ)
- Public procurement case (PPC) - available with Public procurement package. 
- Framework agreement (FA) - available with Public procurement package. 

Tag combination value column, which is available for filtering, is **added to the list pages** of all above mentioned purchase documents, except Framework agreement. Tag combination value column is not displayed in the list page of FAs. Tag combination value field on FA is available on form detail, however, it displays a value from the related public procurement case (**there is no option to manage tags for FA document**). 


# Tag transfer between documents 
---
Tags are transferred from existing purchase document(s) to a new one upon document creation. If one purchase document that contains tags is used to create another (1:1 relation), all tags are transferred to a newly created document. If the relation is n:1 (multiple documents are combined to create a new document), transfer of tags follows the selected option in the procurement setup from chapter [Transfer setup](/Help/Standalone-solutions-\(Suite\)/Document-classification#transfer-setup-for-procurement-documents) (union of tags or no union). 

Possibilities of tag transfer between purchase documents:
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

Changing the tags on documents after a new document has already been created from them does not reflect on already created document. Changing the tag values on the documents after they have been approved in the workflow, does not require the documents to go through workflow again.
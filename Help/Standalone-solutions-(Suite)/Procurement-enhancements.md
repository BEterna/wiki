# Procurement enhancements

Throughout the following sections of this document, functionalities and forms connected with different procurement procedures will be presented, together with their embeddedness with the standard D365O features, required for procurement processes.

Following enhancements are available: 
- Purchase requisition and request for quotation enhancements
  - Allow change of purchase type
  - Auto approve the purchase requisition
 - Purchase agreement enhancements
   - Requester
   - Purchase agreement type
   - Related to agreement
   - Disable editing of effective purchase agreements
   - Change classification
 - Purchase order enhancement
   - Assign subcontractor
- Vendor invoice workflow enhancements
   - Participant is Purchase order line requester
   - Participant is Purchase order or purchase agreement requester
   - Participant is Purchase order purchase placer
   - Participant is Purchase order requester



 
## Vendor invoice workflow enhancements

Vendor invoice workflow is enhanced for additional participant type “Vendor invoice participant provider= that offers four new participants:
   - Purchase order line requester
   - Purchase order or purchase agreement requester
   - Purchase order purchase placer
   - Purchase order requester
 
With this functionality, it is possible to include specific users from purchase orders or purchase agreements into the vendor invoice review process. 

### Participant is Purchase order line requester

If vendor invoice workflow is configured to include approval assignment for participant “Purchase order line requester”, the approval element for vendor invoice that is related to PO(s) goes to the person(s), selected in the Requester field on PO line(s). 
The assignment follows the standard setup of approval policy, for example:
   - if "All approvers" is selected, vendor invoice is assigned to all persons, defined as line requesters; workflow is not continued before all users approve the invoice;
   - if “Single approver” is selected, vendor invoice is assigned to all persons, defined as line requesters; for a workflow to continue, it is sufficient that only one user approves the invoice.
 
### Participant is Purchase order or purchase agreement requester

If vendor invoice workflow is configured to include approval assignment for participant “Purchase order or purchase agreement requester”, the approval element for vendor invoice that is related to purchase order(s) or purchase agreement is assigned to a person(s), selected in Requester field on PO or PA header. The assignment follows the standard setup of the approval policy.

### Participant is Purchase order purchase placer

If vendor invoice workflow is configured to include approval assignment for participant “Purchase order purchase placer”, the approval element for vendor invoice that is related to purchase order(s) is assigned to a person(s), selected in Orderer field on PO header. The assignment follows the standard setup of approval policy.
 
### Participant is Purchase order requester

If vendor invoice workflow is configured to include approval assignment for participant “Purchase order requester”, the approval element for vendor invoice that is related to purchase order(s) is assigned to a person(s), selected in Requester field on PO header. The assignment follows the standard setup of approval policy.
 






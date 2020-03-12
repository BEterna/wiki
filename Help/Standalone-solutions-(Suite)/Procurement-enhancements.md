# Procurement enhancements

Throughout the following sections of this document, functionalities and forms connected with different procurement procedures will be presented, together with their embeddedness with the standard D365O features, required for procurement processes.

Following enhancements are available: 
- Purchase requisition and request for quotation
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

## Purchase requisition and request for quotation enhancements

The procurement process usually begins with Purchase requisitions (PRs) – a standard D365O feature. However, some enhancements in connection with PRs are made for the purpose of the more efficient procurement process. These enhancements are described throughout the following chapters.

### Allow change of purchase type

When RFQ cases are created from PRs, their purchase type is “Purchase requisition” and cannot be changed. The purchase type on RFQs is important, as it defines the outcome (document) that is to be created at the end. Since standard D365O functionality does not allow the change of purchase type on RFQ cases, which were created from PRs, the below-described functionality has been added to allow that.

Open Procurement and sourcing - Setup - Procurement and sourcing parameters.
 
By enabling the “Allow change of purchase type” setting, purchase type on RFQs created from PRs can be manually changed, as long as PR is in status “In review”. Available values in the field:
   - Purchase order
   - Purchase agreement
   - Framework agreement  
 
If “Allow change of purchase type” is enabled, standard Purchase type field on RFQ header is always locked for editing (greyed out):
 
Changing purchase type on RFQ case manually is not allowed if:
   - standard D365O conditions for locking the field are met or
   - RFQ is connected with the public procurement case (available only in AdSuite_Public Procurement package)

 
### Auto approve the purchase requisition

Using this setting, when creating RFQ(s) out of PR(s) with purchase type either “Purchase order” or “Purchase agreement”, after accepting/rejecting all the PR lines, PR is auto-approved – PR header and line status automatically changes to “Closed”. Auto-approval is generated in the name of the user, who performed the acceptance/rejection of the last remaining unprocessed PR line. Auto-approval can be enabled in:

Open Procurement and sourcing - Setup - Procurement and sourcing parameters -> tab Request for quotation, field Auto approve purchase requisition.
 
Reason for using this functionality is to avoid leaving PRs, related to RFQ(s), in review, but instead closing them once all the lines have been either accepted or rejected. When vendor tenders related to all lines from PR are either accepted or rejected, PR status (header and lines) changes to “Closed”.
 
This feature prevents releasing already accepted/rejected PR lines to a purchase order through the standard “Release approved purchase requisitions” functionality and therefore prevents duplicated purchase orders or purchase orders referring to the same PR lines.

## Purchase agreement enhancements

### Requester

An additional field “Requester” has been added to the purchase agreement header to allow the specification of an employee who has requested the creation of a specific purchase agreement. Field Requester allows the selection from the list of all employees.
 
This additional field allows for the person in the field to be included in the vendor invoice review process if adequate participant provider is selected in the workflow configuration.

### Purchase agreement type

For further differentiation of purchase agreements an additional field “Purchase agreement type” has been implemented to determine whether an agreement is an Annex or a stand-alone agreement. Possible values for selection in the field are Agreement and Annex. 
 
If Annex is selected, a new field "Related to agreement" activates (more in the next chapter).
 
### Related to agreement

In relation to the “Purchase agreement type” field, an additional one – Related to an agreement – has been added to the purchase agreement header. This feature allows establishing a relation between an original purchase agreement and its annex. 

Related to the agreement field is active only when the Purchase agreement type selected is “Annex”. It allows the selection of all existing purchase agreements from all legal entities that are of type “Agreement”. 
 
### Disable editing of effective purchase agreements

Standard functionality allows for data on the purchase agreement to be edited regardless of document status. To prevent changes in Effective status, additional functionality is implemented. 

Navigate to Procurement and sourcing - Setup - Procurement and sourcing parameters – tab General -> Select Yes in the Disable editing of effective purchase agreements field.
 
When this parameter is set to Yes, a purchase agreement is locked for editing when in status Effective.
 
When the status is set to On hold, the agreement fields become active for editing.
 
### Change classification

Standard functionality does not allow for purchase agreement classification to be changed (once the record is saved, the field becomes unavailable for editing).
 
With procurement enhancements, it is possible to change the classification if no related Invoice lines or Release order lines exist. Navigate to action pane, button Change classification.
 
Select the desired purchase agreement classification from the drop-down.
 
Confirm the selection.
 
The value in field Purchase agreement classification is changed.
 
Once the related Invoice lines or Release order lines exist, the button Change classification is no longer available.
 
The ability to change classification is also affected by the Disable editing of effective purchase agreements parameter (if the parameter is set to Yes and the agreement is in status Effective, the button to change classification is locked for selection even though there are no related Invoice lines or Release order lines). 

## Purchase order enhancement

### Assign subcontractor 

In standard D365FO, when a purchase order is related to a purchase agreement that has subcontractors, it is not possible to change the vendor account to one of the subcontractors without removing the link to the agreement. Consequently, it is not possible to track agreement fulfillment that would include subcontractors.
 
A new feature “Assign subcontractor” has been added to the purchase order that allows the change of vendor account without removing the link to purchase agreement. Available vendors for selection are the subcontractors from the related purchase agreement.
 
After the subcontractor is assigned (vendor account is changed), the purchase agreement link remains.
 
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
 






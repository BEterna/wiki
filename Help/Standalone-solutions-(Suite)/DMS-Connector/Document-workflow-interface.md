# **Document workflow interface**
Documents in D365FO can have a workflow activated, through which specific workflow steps are assigned to users. 

___

## **Setup**
For a successful workflow integration process, a DMS provider with class name AdDmsGenericBusinessEventProvider in Organization administration > Document management > DMS provider must be configured.
DMS provider enables workflow element to trigger a Business event, that sends data to an external document management system. In order for this to happen, Business event for each document must be configured:
-	Vendor invoice: BE VendorInvoiceApproveBusinessEventAdDMS
-	FTI: BE CustFreeTextInvoiceApproveBusinessEventAdDms
-	Purchase order: BE PurchaseOrderApproveBusinessEventAdDMS
Each Business event needs to be configured for specific legal entity and needs to be connected to a proper endpoint.
Document workflow interface – receival of the approval resolution 
When workflow process is completed in the external document management system, approval result is sent back to D365FO through the custom service CompleteApproval. Approval result can be:
    -	Approved,
    -	Rejected,
    -	Requested change.

___

## **Working with document workflow interface**

The interface introduces an integration workflow element, that enables:
- the assignment of the step to an external document management system 
- and the receival of the performed step resolution from the external document management system.

The workflow process can be therefore configured as an integration process: 
- starting in D365FO and performing as many as necessary internal D365FO steps, 
- then handling the process over through the integration workflow element to an external document management system,
- pausing the D365FO workflow until the resolution from the external document management system is received through the same integration workflow element,
- and finally completing the rest of internal D365FO steps (if they exist) and ending the workflow in D365FO.

Integration workflow elements that are supported within the solution are enabled for the following documents in D365FO:
- Vendor invoice
  - Workflow element Approve vendor invoice in DMS
- FTI
  - Workflow element Free text invoice approve in DMS
- Purchase order
  - Workflow element Approve purchase order in DMS

Based on the approval result from external document system, the process in FO continues accordingly.

Check [Postman collection examples](https://documenter.getpostman.com/view/11980146/2sA3Qv7Vjc)


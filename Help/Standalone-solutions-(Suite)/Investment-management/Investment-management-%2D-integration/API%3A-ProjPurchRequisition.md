

ProjPurchRequisition API creates **header and lines of the Purchase requisition document** for a specific project in the Purchase requisition table. It enables **inserts only**. After successful inserts of records in the Purchase requisition table, an output is provided from D365FO to the 3rd party system. When inserts fail, the error message is provided to the 3rd party system.

The API includes also the possibility to link a purchase requisition line to a selected Purchase agreement provided in the request. This option is available only when the feature **Enable input of Purchase agreement in createPurchReqService and PurchaseRequisitionLineEntity** is enabled in the Feature management of a D365FO environment. This feature enables the API to take the Purchase agreement provided in the request as the proffered one, when there are more than one Purchase agreements available in the D365FO environment to link the purchase requisition line to. If the Purchase agreement from the request does not meet all the standard requirements for linking it to the purchase requisition line, the integration process will fail and an error message will be provided to the 3rd party system.


and validate it according to D365FO rules for libnking a Purchase requisition line to a purchase agreement. When this validations are successfull the Purchase 

Purchase requisition moves through the review process using workflow. **Skip PR submit to workflow** parameter in **Project management and accounting > Setup > Project management and accounting parameters > IM integration > Project requirements** governs how purchase requisition is submitted to workflow:
- If set to **No**, purchase requisition is **immediately submitted within the integration process**.
- If set to **Yes**, purchase requisition has to be **manually** submitted to workflow.


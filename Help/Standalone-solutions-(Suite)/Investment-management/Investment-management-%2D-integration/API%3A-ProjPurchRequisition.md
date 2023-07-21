

ProjPurchRequisition API creates **header and lines of the Purchase requisition document** for a specific project in the Purchase requisition table. It enables **inserts only**. After successful inserts of records in the Purchase requisition table, an output is provided from D365FO to the 3rd party system. When inserts fail, the error message is provided to the 3rd party system.

Purchase requisition moves through the review process using workflow. **Skip PR submit to workflow** parameter in **Project management and accounting > Setup > Project management and accounting parameters > IM integration > Project requirements** governs how purchase requisition is submitted to workflow:
- If set to **No**, purchase requisition is **immediately submitted within the integration process**.
- If set to **Yes**, purchase requisition has to be **manually** submitted to workflow.


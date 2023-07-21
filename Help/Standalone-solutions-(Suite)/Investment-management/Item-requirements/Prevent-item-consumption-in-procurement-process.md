Item consumption from company’s own inventory to a project can happen in different steps for different scenarios. With the out-of-the-box solution, users can immediately consume items on a project when items are received in warehouse (i.e. product receipt for items is generated for purchase order that was created out of an item requirement (IR)). The Investment management package provides configuration that can prevent immediate item consumption to a project when items have been procured for a specific project. In this way, project team member can decide when to actually consume items from inventory to a project (i.e. when should be posted either the packing slip for IR or project item journal). 

Prevention of item consumption from inventory to a project in the procurement process can be configured on Project group (for project) and/or on Item model group (for item). 

![PreventIC01.jpg](/.attachments/PreventIC01-c3b0cec6-631c-4505-add0-2a813afc1946.jpg)

![PreverntIC02.jpg](/.attachments/PreverntIC02-475d2040-7078-483e-81b9-a5e04fde0a44.jpg)

Logic is based on combination of both options, which is explained in the following table for different scenarios. If both options are set to No, the out-of-the-box D365FO logic applies.

_Abbreviations_:
-	PROJ = Project
-	IR = Item requirement
-	MRP = Master planning
-	PO = Purchase order
-	PR = Product receipt
-	INV = Vendor invoice
-	IMG = Item model group
-	PG = Project group


| Scenario | Item model group = NO, Project group = NO | IMG = NO, PG = YES |IMG = YES, PG = NO  | IMG = YES, PG = YES |
|--|--|--|--|--|
| PO without IR for PROJ > PR (or post INV) | Project transaction is posted when vendor invoice is posted. |Project transaction is posted when either new IR or PROJ item journal is posted.  | Project transaction is posted when either new IR or PROJ item journal is posted.| Project transaction is posted when either new IR or PROJ item journal is posted. |
| IR > PO > PR (or post INV)  | System asks users (when posting PR and/or INV), whether they would like to post item consumption on a project immediately. If they select yes, packing slip for IR is posted immediately, otherwise it has to be posted afterwards. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on PG. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on IMG. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on IMG and PG. Project transaction is posted when packing slip for IR is posted. |
| IR > MRP > PO > PR (or post INV) | System asks user, whether he/she would like to post item consumption on a project immediately. If he/she selects yes, packing slip for IR can be posted immediately, otherwise it has to be posted afterwards. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on PG. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on IMG. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting product receipt (or vendor invoice), because prevention is set on IMG and PG. Project transaction is posted when packing slip for IR is posted. |
|IR > TO > MRP > PO > PR (or post INV) | No additional pop-up window appears regarding item consumption on a project when posting PR (or vendor invoice), because no Project ID is defined on PO line. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting PR (or vendor invoice), because no Project ID is defined on PO line. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting PR (or vendor invoice), because no Project ID is defined on PO line. Project transaction is posted when packing slip for IR is posted. | No additional pop-up window appears regarding item consumption on a project when posting PR (or vendor invoice), because no Project ID is defined on PO line. Project transaction is posted when packing slip for IR is posted. |




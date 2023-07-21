To access the **Generated shipments** form, follow the menu _Inventory management > Outbound orders > Generated shipments_ or _Project management and accounting > Periodic > Investment management > Generated shipments_. In this form, users have by default an overview of all completed and not yet posted shipments, which means: 
- Handling status ‘Completed’ stands for completed registration and picking of items per picking route line. 
- Not yet posted shipments have empty Issue document number and these are shipments that, depending on source, means following. For:
   - Item requirements (IR): consumption to project has not yet been posted.
   - Transfer orders (TO): shipment from a warehouse and receipt (including pick) to another warehouse has not yet been posted.

With the list of all generated shipments, storekeepers can easily follow shipments from their warehouses and post consumption from TO or IR within a single step.
Explanation of important fields in this form:
-	**Shipment**: ID of generated shipment by the Process item requirements job
-	**Requested ship date**: automatically transferred from required date on IR
-	**Site, warehouse**: inventory dimensions in shipment line (i.e. Picking route line)
-	**Issue document**: ID of document when posting shipments
-	**Item requirement**: Lot ID of item requirement
-	**Project ID**: ID of project per shipment related to IR
-	**Reference**: either sales order for direct consumption or transfer order for indirect consumption (based on differentiation on IR warehouses).
-	**Reference document**: ID of related Sales order or Transfer order
-	**Reference lot ID**: Lot ID on the Sales order line or Transfer order line
-	**Picking route**: ID of the Picking route document

Explanation of important buttons in this form:
-	**Picking routes**: additional form opens by clicking this button, and it is the same as standard picking routes for standard shipments. It allows users to review picked quantities, split lines and (un)pick items.
-	**Display dimensions**: with this option users can select, which inventory dimensions to display per picking route line.
- **Post shipment**: user must select all lines within selected shipments that he would like to post and then by clicking the Post shipment button, he is posting:
   - Consumption on a project for Sales order reference (direct consumption, i.e. same warehouses on IR)
   - Transfer from a receiving to a consumption warehouse for Transfer order shipment reference (non-direct consumption, i.e. different warehouses on IR)
-	**Unpick and cancel lines**: with this button user does unpicking of automatically picked items and cancelling of picking route lines.
-	**Show**: filtering option to see Posted, Not posted or All generated shipments. This filter applies to the Issue document field.
- **Handling status**: filtering option for standard status of the picking route document - for the Investment management process, important states are following:
   - _Activated_: For order picking the picking route state will be Activated when creating a picking route and not performing an auto-pick.
   - _Started_: Picking has been started, either from the Picking routes when guided pick is used, or when performing the first pick.
   - _Completed_: Picking has been completed. With automatically generated shipments, this is the default status as shipment is created only for items available in inventory that can be automatically picked. 
   - _Canceled_: Quantity on picking route line has been cancelled for the shipment.

![Items.png](/.attachments/Items-5ae803c0-0659-4377-9d02-ea02b58751ba.png)

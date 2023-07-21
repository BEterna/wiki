Following example shows process for the same receiving and consumption warehouse on item requirement (IR). No transfer order (TO) is required nor created for this case. When item is available in stock in consumption warehouse, system automatically generates picking list (shipment) and picking list registration, in order to pick items from inventory for the IR.

Let’s say that the setup is following:
-	Project allocation:
![DDCons01.jpg](/.attachments/DDCons01-463b96d6-ec54-406c-95fb-b982b51af649.jpg)
- Project linking:
![DDCons02.jpg](/.attachments/DDCons02-44f7ce9b-47be-4aa7-8824-831aa47c7db1.jpg)
-	Investment project hierarchy:
![DDCons03.jpg](/.attachments/DDCons03-8526141e-ef4c-49e8-a18f-fb39bbe20a67.jpg)

Item requirement is opened for a project for e.g. 2 pieces. Inventory dimensions defined on item requirement are:
-	project allocation (PA) ‘INV000008’
-	batch ‘BA1122’
-	site ‘3’
-	warehouse ‘38’
-	location ‘38’. 

Receiving warehouse and consumption warehouse is the same.

![DDCons04.jpg](/.attachments/DDCons04-d8f3b2d1-e6b3-4e38-a6ce-68fe56941509.jpg)

![DDCons05.jpg](/.attachments/DDCons05-c26f53aa-a475-4424-8397-be36b900e1d0.jpg)

Available inventory is on following tracking dimensions in warehouse 38:
-	1 piece: 3 – 38 – INV000008 – BA1122
-	1 piece: 3 – 38 – INV000008 – BA1131

Only second dimensions correspond to the IR, therefore only 1 piece will be automatically picked.

![DDCons06.jpg](/.attachments/DDCons06-4b918b10-0429-4dc5-8ab9-07261355c72f.jpg)

Next step is running the ‘Process item requirements’ job, which can be executed in batch (e.g. each day or every hour) without the need for users’ action. This job generates new shipments for item requirements which correspond to the available quantity in inventory.

![DDCons07.jpg](/.attachments/DDCons07-9330f1a6-2f16-4c1f-9cc6-a6f0285d1b7e.jpg)

In the new window, additional filters can be defined (e.g. item number, lot id of requirement, etc.) by selecting the Filter button.

![DDCons08.jpg](/.attachments/DDCons08-dd15e7a2-9058-4fb2-805c-0c74266cf5ca.jpg)

After defining required filters, job can be executed by selecting the OK button.

![DDCons09.jpg](/.attachments/DDCons09-86e54676-274b-45bc-a0b5-e239e5f63d98.jpg)

Infolog message appears regarding picked items.

![DDCons10.jpg](/.attachments/DDCons10-9d68ab8e-be81-4ccb-8887-a56e3fabc7bd.jpg)

To view generated picking registrations (shipments), go to _Inventory management > Outbound orders > Generated shipments_ > select shipment and click Picking routes:

![DDCons11.jpg](/.attachments/DDCons11-5a38e7e7-e1bb-4844-b390-687e2567536b.jpg)

Picking is automatically done on available dimensions, which is in our case:
-	1 piece: 3 – 38 – INV000008 – BA1122

![DDCons12.jpg](/.attachments/DDCons12-eaa2b7fc-1376-414a-b5de-7d0272deea99.jpg)

If we review inventory transactions, we can see that one piece has been picked on the particular dimensions.

![DDCons13.jpg](/.attachments/DDCons13-15eed529-7dba-4859-bb73-43a8e1128db4.jpg)

After all items have been received, users should post project consumption in the Generated shipments overview as explained in the next chapter. No inventory is available for the posted item consumption (in our case only 1 piece has been spent).

![DDCons14.jpg](/.attachments/DDCons14-caa68a22-eb9f-4a2d-8336-ee7c7231d78e.jpg)
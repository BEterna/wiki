Following example shows process for different receiving and consumption warehouses on item requirement (IR), which is the case when e.g. Project manager or other project member receives an item for a project in main warehouse (in this case 66) and it is consumed to a project from terrain warehouse (in this case 77). System automatically creates transfer order (TO) and when item is available in stock in receiving warehouse, system generates picking list (shipment) and picking list registration in order to pick items from inventory.

Let’s say that the setup is following:
-	Project allocation:
![NDCons01.jpg](/.attachments/NDCons01-bd9bf68c-bf7d-467d-bc75-ca67df9fa05b.jpg)
- Project linking:
![NDCons02.jpg](/.attachments/NDCons02-41e2681a-1046-457f-ac86-bbb66ef31764.jpg)
-	Investment project hierarchy:
![NDCons03.jpg](/.attachments/NDCons03-67d3bf29-602b-426a-a681-ed75dddb8aa8.jpg)

Item requirement is opened for a project for e.g. 4 pieces. Inventory dimensions defined on item requirement are:
-	project allocation (PA) ‘INV000006’
-	batch ‘BATCHNR01’
-	site ‘6’
-	warehouse ‘66’. 

Receiving warehouse is 66 and consumption warehouse is 77 (marked as terrain).

![NDCons04.jpg](/.attachments/NDCons04-89c58380-f2c8-42b1-b873-d656c1a075df.jpg)

![NDCons05.jpg](/.attachments/NDCons05-a334bb13-5252-476d-8e9f-58af71183afc.jpg)

Available inventory is on following tracking dimensions in receiving warehouse 66:
-	1 piece: 6 – 66 – INV000006 – BATCHNR01
-	1 piece: 6 – 66 – GEN – BATCHNR01
-	1 piece: 6 – 66 – INV000005 – BATCHNR01
-	1 piece: 6 – 66 – INV000006 – BATCHNR99

Only first two dimensions correspond to item requirement, therefore only 2 pieces will be automatically picked. Planned purchase order will be created via master planning for the rest of the required quantity on IR and when these items will be procured, they can be picked from inventory for IR.

![NDCons06.jpg](/.attachments/NDCons06-f3644902-53c2-47dd-a8de-206d31c1de84.jpg)

Next step is running the ‘Process item requirements’ job, which can be executed in batch (e.g. each day or every hour) without the need for users’ action. This job creates transfer order (TO) per project and warehouses (if such TO exists, it adds lines to existing open TO), it generates picking list for this IR and it completes picking registration for available quantity in the receiving warehouse.

![NDCons07.jpg](/.attachments/NDCons07-666e51fe-dd68-4f25-9d7f-5e45961a5e09.jpg)

In the new window, additional filters can be defined (e.g. item number, lot id of requirement, etc.) by selecting the filter button.

![NDCons08.jpg](/.attachments/NDCons08-16503c66-b86e-49f6-bcb3-7f35ede92a72.jpg)

![NDCons09.jpg](/.attachments/NDCons09-3c88be03-bd59-41b2-b8e4-a234a0f683bd.jpg)

After defining required filters, job can be executed by selecting the OK button.

![NDCons10.jpg](/.attachments/NDCons10-9d90a742-47ad-4285-b0bd-cf248c4e0e72.jpg)

Infolog message appears regarding creating new or adding IR lines to existing TO.

![NDCons11.jpg](/.attachments/NDCons11-ebf17934-3e66-498a-8818-9314096475ee.jpg)

In our example, job automatically generates new TO from warehouse 66 to 77.

![NDCons12.jpg](/.attachments/NDCons12-1eb71e45-d530-499c-892f-48048fcc4e0c.jpg)

To view generated picking registration, go to corresponding Generated shipment and select Picking routes or select created TO and in the Ship tab select Picking list.

![NDCons13.jpg](/.attachments/NDCons13-5a15f413-7b63-4c61-adc3-eed69dce4e43.jpg)

Picking is automatically done on available dimensions, which is in our case:
-	1 piece: 6 – 66 – INV000006 – BATCHNR01
-	1 piece: 6 – 66 – GEN – BATCHNR01

![NDCons14.jpg](/.attachments/NDCons14-a8384490-1750-4d0f-8a01-d8ae55137d66.jpg)

Shipping and receiving of TO is done out of generated shipment by posting shipments as explained in the [Process item requirements](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/94/Process-item-requirements) and in the [Generated shipments](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/102/Generated-shipments) chapters. Note: If item will in meantime become available in stock, new picking list registration will be generated for the same TO line.

When posting shipment from the Generated shipments form, TO will be automatically shipped and received on consumption (terrain) warehouse and default receipt location (if location dimension is required per item). Items are picked on Consumption warehouse after posting Generated shipment.

If we review inventory transactions for the item CAB6655, we can see that 2 pieces are received on dimensions that were previously picked. Note that warehouse 27 is transit warehouse for the warehouse 66.

![NDCons15.jpg](/.attachments/NDCons15-48a51083-1872-465f-aebb-a5420fea0102.jpg)

After all items have been received, users should post project consumption via IR (Post packing slip). No inventory is available after items have been spent for a project. Please refer to previous chapter.
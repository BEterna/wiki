With Investment management package, the Process item requirements job is available that can run on server, e.g. each hour. This job is processing item requirements (IR) for items (excluding service items) that are required for a project on a construction site or from a mobile warehouse. The job handles creation of TO, if warehouses on item requirements differ, and it automatically generates picking lists (shipments) along with picking list registrations when items are available in inventory.

The job will process only item requirements that are covered in corresponding date range. For this purpose, the additional ‘Item requirements processing lead time’ field is available in the Default order settings form on item:

![procesIR01.jpg](/.attachments/procesIR01-3d8ab8ba-03ab-4b01-b2d3-b5f76cef53fe.jpg) ![procesIR02.jpg](/.attachments/procesIR02-11d53f1a-cb0b-4495-83e8-1e109191f806.jpg)
 
Rules regarding Item requirements processing lead time are following:
- If this field is set to 0, IR will be processed. 

- If today’s date is:
   - Equal to or higher than Requested receipt date on item requirement - IR processing lead time, the job will process such item requirement. 
   - Less than Requested receipt date on item requirement - IR processing lead time, the job will not process such item requirement.
- Example of use:
   - IR processing lead time on item is set to 5
   - Requested receipt date on IR is set to 10.1.2020
   - Today’s date is:
      - 4.1.2020 – Process IR job will not process such IR
      - 5.1.2020 – Process IR job will process such IR
      - 6.1.2020 – Process IR job will process such IR
      - 11.1.2020 – Process IR job will process such IR

Job will also skip service items if item requirements would include such items. Example of error message is shown in the following image.

![procesIR03.jpg](/.attachments/procesIR03-8f379f35-9dec-4f1f-a2d8-bcd22379ac6f.jpg)

Picking route status must be set to Activated (please refer to the [Setup – Picking route status](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/90/Setup?anchor=picking-route-status) chapter) for the job to be able to do automatic picking. If either of these parameters is set to Completed, error appears when running the Process item requirements job:

![procesIR04.jpg](/.attachments/procesIR04-8b7e2b82-a7cf-49e5-9df6-ba9ffcf30cc8.jpg)

Before we dive into examples of project consumption, automatic picking of items from warehouses should be explained. Rules for automatic picking list registration of items via item requirements (generated shipments) depend on whether: 
- project is assigned to a specific project allocation (PA) including hierarchy (i.e. implementation projects) 
- additional tracking dimensions are set on item requirement. For example, project manager could require an item with exactly specified serial number, consequently picking for an item requirement cannot be done, if the same item is in stock with another serial number.

**Example for automatic picking of items**

Project ‘A’ is associated with PA ‘A’, project ‘B’ is associated to PA ‘B’ and another PA ‘G’ is defined in code list with no project associated to it. 

| Project ID | Project allocation |
|--|--|
| A | A |
| B| B |
| - | G |

In this example, an item is available in stock on following tracking and storage dimensions:

| Quantity | Site | Warehouse | Project allocation | Batch number |Project allocation description|
|--|--|--|--|--|--|
|1 |6  |66  |A  |X  | Item is available for project A. |
|1 |6  |66  | A | Y |  Item is available for project A.|
|1 |6  |66  |  G|  X| Item is available for any project. |
|1 |6  | 66 |  B|  Y| Item is available for project B. |

Let’s say that we require 4 pieces of this item for project ‘A’ and defined dimensions on item requirement are: 
- site ‘6’
- warehouse ‘66’
- PA ‘A’

With available inventory, automatic picking of 3 pieces of item will be done as follows:
-	1 piece: 6 – 66 – A – X
-	1 piece: 6 – 66 – A – Y
-	1 piece: 6 – 66 – G – X

Let’s now say that we require 4 pieces of this item for project ‘A’ and defined dimensions on item requirement are: 
-	site ‘6’
-	warehouse ‘66’
-	PA ‘A’
-	batch number ‘X’

With available inventory, automatic picking of 2 pieces of item will be done as follows:
-	1 piece: 6 – 66 – A – X
-	1 piece: 6 – 66 – G – X

# Item requirements processing
---
If item is being tracked also on a location, default receipt (for transfer order) and issue location (for posting IR) must be specified on warehouses for the use of auto receive through transfer orders. In the next sample, we will be using WHS 77 for Terrain warehouse, from which we will be consuming items to a project.

![procesIR05.jpg](/.attachments/procesIR05-612123d7-028e-4fe6-a4fc-f078f2fae60d.jpg)

Available inventory is in following warehouses and locations that are not the same as Terrain WHS.

![procesIR06.jpg](/.attachments/procesIR06-15be6fe1-aa7a-4c6b-a287-169d8f6afebe.jpg)

Item requirement contains different receiving WHS (66) and consumption WHS (77) for the quantity of 5.

![procesIR07.jpg](/.attachments/procesIR07-976a1c2e-79d2-4745-9de5-7bb394646ce3.jpg)

![procesIR08.jpg](/.attachments/procesIR08-9e42f9c4-ad70-45a6-bc21-e2e358f04e52.jpg)

The Process IR job automatically generates new TO with picking in WHS 66. New shipments are available in the Generated shipments overview.

![procesIR09.jpg](/.attachments/procesIR09-e6470b0d-da81-4673-b81d-39b4ef4ee701.jpg)

In the next step, the Post shipment action in the Generated shipments overview transfers items from a WHS 66 to a WHS 77 on a default receipt location and picks available items in WHS 77 for this IR.

![procesIR10.jpg](/.attachments/procesIR10-8238b491-bb93-46ff-beff-e0a02da67892.jpg)

Quantity of 5 on IR is now picked and TO has been processed (shipped and received through a transit WHS). Inventory transactions are picked on a default receipt location in a WHS 77.
![procesIR11.jpg](/.attachments/procesIR11-58d3f047-ca5f-4ff5-aa87-3b5f40ac1af3.jpg)

![procesIR12.jpg](/.attachments/procesIR12-c8158256-b0d5-43fb-8816-0d21e4286809.jpg)

On-hand overview shows no available quantity as all pieces have been picked and are therefore meant to be consumed from inventory to a project through IR.

![procesIR13.jpg](/.attachments/procesIR13-26f087af-46b7-4a0d-9c07-f12b9ef81570.jpg)

Inventory transactions for this item before posting packing slip on IR are following:
1.	Lines marked under number 1 are beginning transactions for quantity that was available in inventory.
2.	Lines marked under number 2 are transactions for items picked in WHS 66 and received in transit WHS 27.
3.	Lines marked under number 3 are transactions for items picked in transit WHS 27 and received in WHS 77 in Default receive location (the same as auto-receive option for TOs in standard solution).
4.	Lines marked under number 4 are transactions for items picked on item requirement.

![procesIR14.jpg](/.attachments/procesIR14-dce03c85-afce-449f-9070-1076149b2a84.jpg)

The next step is posting packing slip on IR, which posts consumption on a project. The quantity of 5 will be delivered after posting.
![procesIR15.jpg](/.attachments/procesIR15-1982fe57-6c34-4170-8d39-cc8b5f744910.jpg)

![procesIR16.jpg](/.attachments/procesIR16-c85e84d6-0467-4ea5-a01b-df65b6927562.jpg)
Issue inventory transactions for this item after posting packing slip on IR are now in status Sold for WHS 77 and default issue location.

![procesIR17.jpg](/.attachments/procesIR17-d16bcd3e-4d12-48ba-832a-92599ad8582c.jpg)

On hand overview after posting consumption from inventory to a project shows no lines.

![procesIR18.jpg](/.attachments/procesIR18-7280d197-ca2e-494e-9caf-f4342d199634.jpg)

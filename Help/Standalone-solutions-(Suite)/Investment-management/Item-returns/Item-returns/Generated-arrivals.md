For more details about when arrivals are being generated, please refer to the previous chapter [Post item return](/Help/Standalone-solutions-\(Suite\)/Investment-management/Item-returns/Item-returns/Post-item-return). 

Generated arrivals are available in _Inventory management > Investment management > Generated arrivals_. A list of non posted generated arrivals is shown by default. Using the Show option user can see already posted, not yet posted or all generated arrivals. Generated arrivals overview contains records from shipped transfer orders that wait for receive. Only transfer order lines that were created out of item returns are shown in this page. 

![Items (3).png](/.attachments/Items%20(3)-52559e9a-3e83-4f4f-83b6-8d038d1175bc.png)

Explanation of fields:
- Lot Id – Lot Id from transfer order
- Date – date of item return
- Receipt document – Id of the Receipt document generated from the number sequence when arrival is posted
- Receipt document date – the date when arrival was posted
- Item return – Id of item return from which transfer order has been created
- Project Id – same as on corresponding item return
- Item number – same as on corresponding item return
- Transfer number – number of created transfer order
- Shipped quantity –  quantity that was automatically shipped with posting item return
- Scrap quantity – if items were broken/lost during transport to a warehouse, scrap quantity can be specified in this field
- To site and To warehouse – to which warehouse are we receiving items
- Update type (can be personalized) – Shipment or Receive with corresponding inventory dimensions that were shipped and later received:
   - By default value is **Shipment** and it shows all not yet posted arrivals that were shipped with storage dimensions (site, warehouse, and location) of From warehouse on the transfer order.
   - **Receive** value shows items and quantities that were received (or scrapped) with storage dimensions of To warehouse on the transfer order.
- Show – available values are Posted, Not posted, All. 
   - **Posted**: shows received transfer orders and items. 
   - **Not posted**: is set by default and shows shipped transfer orders and items that wait to be received in a warehouse.
   - **All**: shows shipped and received records – note that one posted arrival has two records (shipped and received) with corresponding inventory dimensions.
- Display dimensions - user can add inventory dimensions to be shown on the list that shows  dimensions on which items were picked in the From warehouse if arrival was not yet posted.
- Registration - user can manually choose a different location when receiving returned items. When clicking on the registration button, the registration form for receipt of the transfer order on the line will be opened. Users can manually change the location for the whole quantity, or only for some using split function.

![Items (4).png](/.attachments/Items%20(4)-c4e3a8b7-fe28-494e-904e-abb247d7793a.png)

The **Post** button receives items to a To warehouse on transfer order and other inventory dimensions that were picked when shipping transfer order. Functionality for posting is the same as when manually receiving transfer orders. If the posting date is specified, this is the date of posted transactions. When arrival is posted, the Receipt document and date are populated and a report can be printed out. Only inventory dimensions that were displayed in the overview of all Generated arrivals are also populated in the printout. Already posted arrival documents can be printed out once again.

![Items (5).png](/.attachments/Items%20(5)-a60a76a5-7aff-4141-aa99-422b8b0da5b6.png)



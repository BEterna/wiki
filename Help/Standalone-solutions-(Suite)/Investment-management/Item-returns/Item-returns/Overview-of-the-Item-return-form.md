Clicking Item return number in the list of all Item return documents, the Item return form opens. Buttons on this form can differ based on selection of Type:
- ## Common buttons:
   - Item return (mandatory) – Id of the Item return document generated from the number sequence
   - External Id – number provided from 3rd party system, if reversal of the quantity was made in external system
   - Return date (mandatory) – date of item returns; if type is Reverse then only posted project transaction on this or older date can be reversed, not also transactions with newer date
   - Project ID (mandatory) – project Id for returning items
   - Item number (mandatory) – item number to be returned to inventory or cancelled can be only product type that is stocked
   - Return quantity (mandatory) – number must be positive and higher than 0
   - Type (mandatory) – Reverse or Cancel as explained in introduction to Item returns
   - Inventory dimensions – based on selected item, tracked dimensions are mandatory for the Reverse type and only site and warehouse are mandatory for the Cancel type. If type is:
      - **Reverse** – functionality will search specified inventory dimensions that are exactly the same as on inventory transactions that belong to posted project transactions when proposing project transactions
      - **Cancel** – functionality will search specified inventory dimensions that correspond to inventory dimensions on item requirements including Receiving warehouse and belonging picked or reserved inventory dimensions on Generated shipments when proposing item requirements. If for the Cancel item return type, selected warehouse on item return has Investment management type:
         - _Terrain or Moving_ – items will remain on a terrain warehouse if any transfer order’s generated shipment has already been posted and items will not be reserved anymore for a particular project (=item requirement) when posting item return.
         - _Default_ - if any transfer order’s generated shipment has already been posted, a new transfer order will be created and shipped from the original transfer order terrain warehouse to a default warehouse, specified in Item return lines when posting item return. Actual arrival of items in newly created transfer order is posted in the Generated arrivals overview. If transfer order’s generated shipments have not yet been posted, then only quantity is cancelled on shipment, transfer order and item requirement.

- ## Buttons available only for type **Reverse**:
   - Return warehouse – in this field we tell system to which warehouse will be items returned:
      - If return warehouse is empty, then project item journal is posted (with negative qty) to warehouse specified in the Inventory dimensions tab on item return
      - If return warehouse is defined, then project item journal is posted (with negative qty) to warehouse configured in the Item return transfer warehouse field in the Project management and accounting parameters and transfer order is shipped from Item return transfer warehouse to Return warehouse specified in Item return. Arrival of items to final destination is posted in the Generated arrivals overview
   - Financial dimensions – if financial dimensions are specified, they have priority over financial dimensions on posted project transactions. Empty mandatory financial dimensions are merged from originally posted project transactions that are being reversed.
   - Project transactions and the Propose button – when clicking Propose, system will propose posted project transactions that match inventory dimensions and can be reversed. User can also manually change proposed transactions and quantities by selecting New/Delete. System will check actual available quantities once again when posting item return.

      ![Items (1).png](/.attachments/Items%20(1)-8caa9dc2-6717-4c88-81bc-198f2e26c038.png)

- ## Buttons available only for type **Cancel**:
   - Item requirements and the Propose button - when clicking Propose, system will propose open item requirements that match inventory dimensions and can be (partially) cancelled. User can also manually change proposed item requirements and quantities by selecting New/Delete. System will check actual available quantities once again when posting item return.
   - **Note**: tracking dimensions that are specified on item requirements may differ from tracking dimensions (picked or ordered) on transfer order and its related inventory transactions. Therefore, when we are cancelling quantity on item requirement that has specified tracking dimensions and existing related transfer orders, in item return document we have to specify picked tracking dimensions from transfer order or we can specify only storage dimensions in order to cancel also quantity on item requirement.

      ![Items (2).png](/.attachments/Items%20(2)-147a89b9-69dc-446f-952a-db443190f8ea.png)

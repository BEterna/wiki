The Post button on Item return opens new pop-up form, where user can also propose item requirements or project transactions for multiple item returns (in this case the Propose parameter must be set to Yes). Posting action does following for the type:
- **Reverse**:
   1. Post project item journal with following values in line:
      - negative quantity
      - inventory dimensions as specified in item return lines if there is no Return warehouse specified, otherwise posted to Item return transfer warehouse storage dimensions and tracking dimensions as specified in item return lines
      - financial dimensions as specified in item return lines or original project transaction
   1. Create transfer order from previously posted inventory dimensions to a Return warehouse (with same tracking dimensions)
   1. Ship created transfer order
   1. Create Generated arrival lines for storekeeper to post arrival of items in Return warehouse (that was specified in item return header and is also same as To warehouse on transfer oder)

- **Cancel**:
   1. Cancel (whole quantity) or update deliver remainder (partial quantity) on item requirement
   1. Cancel existing generated shipments (whole or partially)
   1. Cancel (whole quantity) or update deliver remainder (partial quantity) on existing transfer orders
   1. If warehouse in Inventory dimensions in item return line does not have investment management type Terrain, then also: 
      - Create transfer order for quantity that was already transferred to a construction site (terrain). Transfer order is created in order to transfer quantity from terrain warehouse to a warehouse specified in inventory dimensions on item return line.
      - Ship created transfer order.
      - Create Generated arrival lines for storekeeper to post arrival of items in warehouse, that was specified in inventory dimensions on item return line


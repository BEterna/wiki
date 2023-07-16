New fields have been added to the dialogue window of creating a new item:
- Checkbox **Create from the procurement category**: if marked Yes, the user can select the procurement category from which to create the item.
- Category drop-down menu, where the user can **select a procurement category**.
- Item model group, Item group, Storage dimension, Tracking dimension, Buyer group, Sales taxation – Item sales tax group, Purchase taxation – Item sales tax group fields are **defaulted from the selected procurement category**.
 - A button **“+”** to open a new window that enables the user to **define attribute values**, for the attributes in the selected procurement category. 
- A user enters/selects values for all attributes that are marked as Required for catalog in the selected procurement category. **During this value selection, the Product name, Name, and Search name are simultaneously generated.**
 
When the user confirms the released item creation:
- The new item has the generated name from the combination of the procurement category and specified attribute values.
- The new item is automatically related to the selected procurement category.
- The new item has all the defined required attributes.

**Validations** on released item:
- The system validates if any other item with the same combination of procurement category and attribute values exists and if such item already exists the functionality prevents user to create item duplicate. 
- Attributes can not be deleted or edited once on the Released item that was created with the Item configurator functionality. 
- Released items can not be removed from the Procurement category, nor can the category be removed from the item. 
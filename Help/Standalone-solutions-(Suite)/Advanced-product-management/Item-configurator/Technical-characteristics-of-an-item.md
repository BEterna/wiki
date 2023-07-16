#Setup
---
##Product information management parameters
Item configurator functionality can be enabled or disabled in _Product information management parameters > General > Item configurator_. 
 
When the parameter Item configurator is enabled, items, created with this functionality, are marked as created with Item configurator, therefore all the controls listed in the document apply to those items. When the Item configurator functionality is turned off, controls enabled with the item configurator still remain.  

##Attribute type
Technical characteristics are entered though Attribute types and Attributes. 

A new field **Unit class** with a drop-down menu for selection is added to _Product information management parameters > Setup > Categories and attributes > Categories and attributes > Attribute types_. The standard field Unit has been disabled, and a new **Unit** field has been added to the attribute page, where the list of units in the drop-down menu correlates to the selected Unit class on the Attribute type.  

Changing the unit class or deleting the Attribute type is disabled once the Attribute type is related to the Attribute. 
 
##Attributes
A new field **Unit** with a drop-down menu for the unit code list has been added to the _Product information management parameters > Setup > Categories and attributes > Attributes_. List of unit values that is possible for selection is filtered according to the value selected in the field Unit class on the related attribute type.
 
Deleting the attribute or changing the Unit is disabled once the Attribute type has been used in the Procurement category.

#Procurement categories 
---

Attributes are specified on procurement categories, tab _Product attributes_. When an attribute is marked as **Required for catalog**, its value has to be specified upon item creation, regardless of its use in the name. 

A new column **Position in name** is added for defining which attributes are included in the generation of the product name and in which order. This value can be defined only if the attribute is marked as Required for catalog. The value in field Position in name can be 0, meaning that the attribute value is not part of the item name, but is still required for the item creation. 

Upon clicking the button _“+Add”_ a wizard with 3 steps, leads the user through the process of:
1. Adding attributes to the procurement category.
1. Setting up properties (required for catalog, position in name) of attributes in the procurement category.
1. [Subsequently adding attributes](https://dev.azure.com/DynamicsUIM/D365UIM/_wiki/wikis/D365UIM.wiki/39/Subsequently-adding-new-attributes-to-procurement-category?anchor=subsequently-adding-new-attributes-to-the-procurement-category) in case there are already existing products associated with the procurement category (see Subsequently adding new attributes to the procurement category).
 
As a result, selected attributes are added to the procurement category.
 
A new tab **Default values for product** is added to the Procurement category form. Fields in the new tab are the following (see below) and represent the default values for an item when the item is created from procurement category using item configurator:
- Item group
- Storage dimension group
- Tracking dimension group 
- Item model group
- Buyer group
- Sales taxation – Item sales tax group
- Purchase taxation – Item sales tax group
 
##Validations
Validations for the procurement category:
- The property Required for catalog cannot be changed if procurement category was already used for any item creation with the item configurator logic; otherwise, it can be deleted.
- Once an item is created using procurement category, the order of the fields that specify the position in the name cannot be changed. If it has not yet been used, it can be changed or deleted. 
- The existing attribute cannot be deleted from procurement category if already used for item creation with the item configurator logic for this procurement category. 
- Items created with item configurator are automatically added to procurement category and as such cannot be deleted from the procurement category not can the category association be deleted from item. 
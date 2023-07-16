# Setup
---
The list of required configurations for Insurance policies is listed below. They can be found in the **Fixed assets > Setup > Insurance** menu. Configured code lists can be selected on Insurance policy in the process of creating a new insurance policy.

## Insurance types
1. Go to Fixed assets > Setup > Insurance > Insurance types.
2. **Add code lists** for Insurance types.

## Insurance premium types
1. Go to Fixed assets > Setup > Insurance > Insurance premium types.
2. **Add code lists** for Insurance premium types.

## Insurance coverage types
The Insurance coverage types table enables linking Insurance types with Insurance coverage types.
1. Go to Fixed assets > Setup > Insurance > Insurance coverage types.
2. **Add code lists** for Insurance coverage types.

## Damage causes
1. Go to Fixed assets > Setup > Insurance > Damage causes.
2. **Add code lists** for Damage causes.

## Insurance coverage type – Damage cause links
The Insurance coverage type – Damage cause links table provides a full list of all Insurance coverage type – Damage cause links.
1. Go to Fixed assets > Setup > Insurance > Insurance coverage type – Damage cause links.
2. **Add possible Insurance coverage type and Damage cause combinations.**

## Insurance roles
1. Go to Fixed assets > Setup > Insurance > Insurance roles.
2. **Add code lists** for Insurance roles.

## Generic insurance entity types
This table represents code lists of Generic insurance entity types. Insurance entity types that can be selected on an insurance policy are **Fixed asset, Project, Person, Worker and Other**. When option **Other** is selected in Insurance policy, under the Insurance coverage fast tab, code lists from Generic insurance entity types can be selected.
1. Go to Fixed assets > Setup > Insurance > Generic insurance entity types.
2. **Add code lists** for Generic insurance entity types.

# Creating an insurance policy
---
To create a new insurance policy, navigate to Fixed assets > Insurance > Insurance policy.
The Insurance policies menu shows all created insurance policies. 

Create new Insurance policy by clicking the button **New**. Following fields are available:

### **General** fast tab:

|Field|Description  |
|--|--|
|**Number** |Insurance policy number  |
| **Vendor account** | Drop-down code list of vendors. Insurance policy vendor is usually insurance company that issued insurance policy. **Combination of Number and Vendor account represents a unique insurance policy identifier**. |
|**Description**  | Insurance policy description  |
| **Insurance type** |  Drop-down code list of Insurance types|


### **Details** fast tab:

| Field | Description |
|--|--|
| **Policy amount** |  Amount paid for policy|
| **Currency**  | Drop-down code list of currencies  |
| **Coverage amount** | Policy coverage amount |
| **Deductible franchise** | Amount of deductible franchise. If entered, this amount represents company’s participation in covering granted damages of occurred loss event connected to the insurance policy. |
| **% deductible** | Percent of deductible franchise. If entered, this percent represents company’s participation in covering granted damages of occurred loss event connected to the insurance policy. |
| **Effective date** | Policy’s effective date |
| **Expiration date**  | Policy’s expiration date |
| **Insurance premium type** | Drop-down code list of Insurance premium types  |
| **Insurance role** | Drop-down code list of Insurance roles |

### **Damage cause coverage** fast tab:

|Field  | Description |
|--|--|
| **Insurance coverage type**  | Drop-down code list of Insurance coverage types linked to the selected Insurance type in General fast tab |
| **Damage cause** | Drop-down code list of Damage causes linked to the selected Insurance coverage type |
| **Coverage amount** | Coverage amount per Insurance coverage type – Damage cause combination |
| **Check amounts** | Yes/No checkmark. This checkmark prevents that the sum of Granted damages of dependent loss events exceeds Granted damage of parent loss event connected to the same insurance policy. |

**Available coverage** – This button checks all loss events connected to the insurance policy and shows how much coverage is released and still available per Insurance coverage type and Damage cause. Button opens a new pop-up window, with default filter on Closed loss events. Other filters can be added manually. 

After confirming selected filtering options, a new table with following columns is displayed:
- **Insurance coverage type** – Insurance coverage types entered in insurance policy
- **Damage cause** – Damage causes entered in insurance policy
- **Total coverage** – Total coverage amounts entered in insurance policy
- **Released coverage** – sum of Granted damages from all loss events that are included after filtering (default filter on closed loss events) per Insurance coverage type and Damage cause
- **Available coverage** = Total coverage – Released coverage

### **Insurance entity type** fast tab:

The Insurance entity type fast tab enables adding and deleting Insurance entity types, which represent entities that are insured in the policy. Based on the selected Insurance entity types, in the next fast tab Insurance coverage, insurance entities are selected. Possible options for selection in the Insurance coverage fast tab are:
- **Fixed asset** – fixed assets can be selected
- **Project** – projects can be selected 
- **Worker** – workers can be selected
- **Person** – people that are parties (in the Common menu in D365FO) can be selected 
- **Other** – Generic insurance entity types can be selected

**Within the single insurance policy, multiple insurance entity types can be added.**

### **Insurance coverage** fast tab:

Insurance coverage fast tab enables adding and deleting insurance entities that are part of insurance policies. The fast tab contains following buttons:
- **Create Insurance coverage lines** – this button opens a new pop-up for creating Insurance coverage lines based on the selected Insurance entity type in the previous fast tab.
- **Delete** – delete selected rows in the table below


**Create coverage lines** pop-up enables adding following information: 

- **Insurance coverage type** – select one of the insurance coverage types specified in the insurance policy
- **Insurance entity** – select the entity that is insured, based on the selected Insurance entity type in the previous tab.
- **Value source** – field is available only when insuring fixed assets. If Values source is **Acquisition value**, system automatically calculates Acquisition value of the FA up to insurance policy’s Effective date (transactions posted on the effective are also included). Acquisition value includes Acquisition, Acquisition adjustment, Write-up adjustment and Write-down adjustment transaction types. If Value source is **Net book value**, system automatically calculates Net book value of the FA on the insurance policy’s Effective date (transactions posted on the effective date are also included). If Insured by is **None**, Insured value is 0 and it can be changed manually.

After adding insured entities, the table shows basic information about the entities (ID, Name, etc.) and:
- **Insurance coverage type** – selected Insurance coverage type
- **Value source** – selected value source for fixed assets.
- **Insured value** – calculated Insured value based on the selected Value source for fixed assets. The amount can be changed, if needed, or added manually for other insurance entity types.
- **Insured by market value** – Yes/No checkmark showing whether the fixed asset is insured by market value
- **Market value** – market value can be entered manually, if needed.
- **Valuation value** – valuation value can be entered if the fixed asset was evaluated by valuator.
- **Valuation date** – valuation date can be entered if the fixed asset was evaluated by valuator.








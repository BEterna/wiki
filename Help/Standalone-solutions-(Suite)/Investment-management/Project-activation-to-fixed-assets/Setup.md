# Number sequence for Project activation proposal to fixed asset
---
Firstly, number sequence for Project activation proposal to fixed asset must be configured. Navigate to _Organization administration > Number sequences > Number sequences_ and click Number sequence to create a new number sequence.

Furtherly define:
- Number sequence code and Name
- Scope parameters
- Segments
- References (Choose Area: _Investment management_; Reference: _Activation proposal_).

# Project activation proposal parameters
---
In order to configure the Project activation proposal parameters navigate to _Project management and accounting > Setup > Project management and accounting parameters_. 

![Items.png](/.attachments/Items-86c5cc7b-d6c0-493b-9f10-848646086767.png)

Under the Project activation tab, following parameters can be set up:
- **Detail level**:
   - _Detail_: when posting activation proposal, this option will create voucher transaction for each main account and financial dimensions from the original transactions, please refer to the example below:

      ![Items (1).png](/.attachments/Items%20(1)-3b0c26dc-7097-452e-b007-4e318bb2d7a0.png)

   - _Summary_: when posting activation proposal, this option will create one voucher transaction for the same main account and financial dimensions from the original transactions, please refer to the example below:

      ![Items (2).png](/.attachments/Items%20(2)-0c075c44-743e-4d3f-b57f-84f5ca0f8478.png)

- **Voucher series for projects**: voucher number for posted activation proposal from project to project
- **Voucher series for fixed assets**: voucher number for posted activation proposal from project to fixed asset
- **Project worker responsible** is mandatory on workflow submit: if this option is set to Yes, then Project manager must be defined on project in order to submit Project activation proposal to workflow (WF). Otherwise, user will receive an error when submitting the document to WF as shown on the image below. If this option is set to No, then there is no validation for the Project manager field on a project.

   ![Items (3).png](/.attachments/Items%20(3)-aeac2d24-e274-47c2-9855-0cc4c157d933.png)

- **Transfer financial dimensions from project to fixed asset**: If this option is set to Yes, then financial dimensions from project are transferred to new fixed assets created without default financial dimensions in the activation proposal form. If a fixed asset was previously created in the Fixed assets form or if the financial dimensions are added to FA in the form for creating new fixed assets in the Activation proposal, then financial dimensions from the project are not transferred to fixed asset, although the Transfer financial dimensions from project to fixed asset is set to Yes. Similarly, for all fixed assets that already have some posted transactions, financial dimensions from the project are not transferred, although the Transfer financial dimensions from project to fixed asset is set to Yes.
If this option is set to Yes, it will influence the Project activation to fixed asset postings in the following way:
   - If new fixed asset is created in the Project activation proposal form without default financial dimensions: voucher transactions with posting type “Fixed asset” will have financial dimensions from the project.
   - If new fixed asset is created in the Project activation proposal form with default financial dimensions: voucher transactions with posting type “Fixed asset” will have default financial dimensions added during creation of the new FA.
   - If new fixed asset is created in the Fixed assets form without default financial dimensions on the FA book: voucher transactions with posting type “Fixed asset” will not have any financial dimensions.
   - If new fixed asset is created in the Fixed assets form with default financial dimensions on the FA book: voucher transactions with posting type “Fixed asset” will have default financial dimensions from FA book.
   - In any case, voucher transactions with posting type “Project activation” will have financial dimensions from the project.
- **Prevent elimination through estimates**: If this option is set to Yes, standard elimination through estimates is prevented. Buttons Eliminate and Reverse elimination are greyed out in 
All projects > Manage > Estimates.




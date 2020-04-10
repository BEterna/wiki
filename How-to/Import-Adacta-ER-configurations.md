There is a number of configurations that were developed as part of different Adacta solutions. Some of them are dependent on standard MS configurations. Therefore it is important to import configurations in following order:

1. Import Microsoft configurations from Operations resources repository. Go to Workspaces > Electronic reporting > Configuration providers > Microsoft > Repositories > Operations resources. Following MS configurations need to be imported first:


|**Configuration**| **Version** |
|--|--|
|EU Sales list model | 1 |
|Intrastat model |1  |
|ISO20022 Credit transfer |1.1  |
|Ledger accounting reports  | 1 |
|Payment model  | 1 |

2. Import Adacta configurations from Adacta repository. There are separate repositories available for each package. Import  repositories for the packages you are using. Go to  Workspaces > Electronic reporting > Configuration providers > Adacta > Repositories > pick repository according to installed packages. Available repositories: 

- Adacta localization
- Adacta localization (Bank)
- Adacta localization (Fiscalization)
- Adacta Suite (Dunning)





#**Create and send enforcement or enforcement package to court**

Enforcements can be sent to court as single enforcement or as a package with multiple enforcements. This functionality is only available for country region SI.

##**Enforcement settings**
Credit and Collections/Setup/Enforcements/Enforcements settings/General
Web service setup
|**Parameter**|**Description**|**Value (for test server)**|
|--|--|--|
|**Web server for sending**| Web server for submitting the enforcement packets to court|https://evlozisce-test.sodisce.si/axis2/services/PackageProposalService
|**Web server for checking**|Web server for checking the enforcement packets with the|https://evlozisce-test.sodisce.si/axis2/services/ProposalStatusService
|**Enforcement proposal electronic reporting format**|Enforcement proposal electronic reporting format (XML)|Enforcement proposal format (Electronic reporting)

Note: Prior to selecting the Enforcement proposal electronic reporting format in enforcement settings, it needs to be configured in Electronic reporting workspace. Configure a new repository with a Configuration repository type: »Adacta Suite (Dunning)« and import the contained electronic reporting formats. 
Links for web servers can be found on https://evlozisce.sodisce.si/ . 


##**Single enforcement**
Filing single enforcement can be created in the enforcement proposals tab. Enforcement can be selected in the grid and exported to the XML document.
1.	Credit and collections/Enforcements/Enforcement proposals
2.	Export -> Export proposal
3.	Enter file name
4.	»OK«

##**Package with multiple enforcements**
1.	_Credit and collections/Enforcements/Enforcement proposals_
2.	Chose enforcement in draft mode
3.	Enforcement packet -> Assign to packet
4.	New packet/existing packet
5.	Assign to packet
6.	_Credit and collections/Enforcements/Enforcement packets_
7.	Send packet / Export packet
8.	Choose file name
9.	»OK«

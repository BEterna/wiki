Standard D365O feature in terms of the interest calculation allows calculating daily interests, but does not account for the leap years, as it considers all years equally long.

This localization feature enables an additional interest calculation type “Day (Actual year)”, which recalculates the interest amount. It considers the actual number of days in each year, including the leap years. Calculation type ”Day (Actual year)” calculates interest according to the following formula:

interest rate = amount * (annual interest rate / number of days in a calendar year) * number of overdue days

[Detailed document](https://adacta.sharepoint.com/:w:/r/sites/ERP-Product-Development/Shared%20Documents/D365FO%20Localization%20documentation/D365O%20LOC_Interest%20calculation%20type.docx?d=wbb4e0de15d7342a1893ba4965ad08755&csf=1&e=cRhs7E)
Standard D365O feature in terms of the interest calculation allows calculating daily interests, but does not account for the leap years, as it considers all years equally long.

This localization feature enables an additional interest calculation type “Day (Actual year)”, which recalculates the interest amount. It considers the actual number of days in each year, including the leap years. Calculation type ”Day (Actual year)” calculates interest according to the following formula:

interest rate=amount * (annual interest rate number / number of days in a calendar year) * number of overdue days

[Detailed document](http://axweb/D365O%20Localization%20Documents/D365O%20LOC_Interest%20calculation%20type.docx?Web=1)
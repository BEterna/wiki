# Main account statement 

This topic provides country/region-specific information about the statement of the legally required information that needs to be available for main accounts in order to comply with Croatian legislative requirements. The main account statement provides information, which legal entities in Croatia need to provide if required so by local authorities according to Croatian Accounting law (Official gazette 78/15, 134/15,120/16: Article 12., Section 9.), which specifies the minimum information, legally required to be included on the main account statement.

This localization feature enables Croatian legal entities to prepare the account statements for each Main account with the legally required information. After the generation, the main account statement can be exported to various formats.

## Legal requirements

In accordance to the Croatian Accounting law (Official gazette 78/15, 134/15,120/16: Article 12., Section 9.) the following are minimum requirements for Main account statement:

(9) Izvadak za pojedini konto mora sadržavati najmanje sljedeće:
1. naziv, odnosno ime i prezime te sjedište, odnosno adresu poduzetnika
2. brojčanu oznaku konta
3. naziv konta
4. razdoblje na koje se odnosi
5. početno stanje ako postoji
6. za svaku knjiženu promjenu: jedinstvenu identifikacijsku oznaku knjigovodstvene promjene, datum knjigovodstvene promjene, datum knjiženja, opis sadržaja promjene, dugovni ili potražni iznos, oznaku pripadajuće knjigovodstvene isprave
7. zaključni ukupni dugovni i potražni promet za razdoblje na koje se izvadak odnosi
8. stanje konta na kraju razdoblja.
Izvor: Zakon o računovodstvu NN 78/15, 134/15,120/16: Članak 12., Točka 9.



## **Generate report**
---

1. Open General ledger - Inquiries and reports - Croatia - Izvadak konta.
2. By clicking on the “OK” button, statement is generated
3. Report can also be accessed from General ledger - Ledger reports - Ledger transaction list.

_NOTE: Users will be forced to tun the report in batch when the selected period will exceed 31 days._

_NOTE: The product functionality is based on standard Microsoft D365FO framework (used for Dimension statement report). As Microsoft disabled the ability to run this kind of reports when the selected period is larger than 31 days, there is possibility that even when running the Main account statement in batch it could end in unsuccessful result. In such cases, the approach based on exporting data via data entities and prepare a BI report outside D365FO, must be used)._

















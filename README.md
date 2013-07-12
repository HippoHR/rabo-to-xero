rabo-to-xero
============
Formats the Dutch Rabobank CSV format for bank statements so it can be imported by Xero.

Input format (http://www.rabobank.nl/images/formaatbeschrijving_csv_kommagescheiden_nieuw_29539176.pdf, http://www.sepa.nl/):

1.	REKENINGNUMMER_REKENINGHOUDER   IBAN number.
2.	MUNTSOORT
3.	RENTEDATUM                      YYYYMMDD
4.	BY_AF_CODE                      C or D
5.	BEDRAG                          This is always a positive number, for both credits and debits.
6.	TEGENREKENING
7.	NAAR_NAAM
8.	BOEKDATUM                       YYYYMMDD
9.	BOEKCODE
10.	FILLER
11.	OMSCHR1
12.	OMSCHR2
13.	OMSCHR3
14.	OMSCHR4
15.	OMSCHR5
16.	OMSCHR6
17.	END_TO_END_ID
18.	ID_TEGENREKENINGHOUDER
19.	MANDAAD_ID

Target format:

1.	REKENINGNUMMER_REKENINGHOUDER   IBAN number.
2.	MUNTSOORT
3.	RENTEDATUM                      YYYYMMDD
4.	BY_AF_CODE                      C or D
5.	BEDRAG                          This is a positive number for C's, and a negative number for D's.
6.	TEGENREKENING
7.	NAAR_NAAM
8.	BOEKDATUM                       YYYYMMDD
9.	BOEKCODE
10.	FILLER
11.	OMSCHR1                        All description lines are pasted together into this field. It will also include the END_TO_END_ID and ID_TEGENREKENINGHOUDER
12.	MANDAAD_ID

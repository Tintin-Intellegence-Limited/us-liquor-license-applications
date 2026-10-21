# New restaurant and bar liquor license applications (US, last 30 days)

A free, machine-readable list of restaurants and bars that recently filed for a liquor license in New York City, Los Angeles and five Texas metros. A liquor license application is usually the earliest public sign that a new restaurant or bar is about to open, often weeks before it opens its doors.

This dataset is published by [PourWire](https://pourwire.com/?utm_source=github&utm_medium=dataset), which tracks these filings every day for insurance agents, POS resellers, equipment suppliers and food distributors who sell to new venues.

**Coverage:** 176 filings from 2026-09-21 to 2026-10-19.

| Metro | Filings | Live list (updated daily) |
|---|---|---|
| Houston | 53 | [pourwire.com/houston/liquor-license-applications](https://pourwire.com/houston/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Dallas-Fort Worth | 42 | [pourwire.com/dallas-fort-worth/liquor-license-applications](https://pourwire.com/dallas-fort-worth/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| New York City | 30 | [pourwire.com/new-york/liquor-license-applications](https://pourwire.com/new-york/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Austin | 23 | [pourwire.com/austin/liquor-license-applications](https://pourwire.com/austin/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| San Antonio | 18 | [pourwire.com/san-antonio/liquor-license-applications](https://pourwire.com/san-antonio/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Los Angeles | 5 | [pourwire.com/los-angeles/liquor-license-applications](https://pourwire.com/los-angeles/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Waco-Temple | 5 | [pourwire.com/waco-temple/liquor-license-applications](https://pourwire.com/waco-temple/liquor-license-applications?utm_source=github&utm_medium=dataset) |

## File

`data/filings-last-30-days.csv`, one row per venue:

| Column | Meaning |
|---|---|
| filed | Date of the earliest filing we have for the venue (YYYY-MM-DD) |
| metro | Metro area slug |
| city | City |
| name | Trade name as filed |
| street | Street name (house numbers removed) |
| type | bar, restaurant or coffee shop |

## Sources

Public records from the Texas Alcoholic Beverage Commission (TABC), the New York State Liquor Authority, NYC permit data, and the California Department of Alcoholic Beverage Control. Chains, hotels, gas stations, grocery and liquor stores are filtered out, so the list is mostly independent restaurants and bars.

## Want the full record?

The live lists on pourwire.com add the full address, license type, filing status and, where available, the owner contact, and they update every day. There is a free sample for every metro: [pourwire.com](https://pourwire.com/?utm_source=github&utm_medium=dataset).

## License

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please credit "PourWire (pourwire.com)".

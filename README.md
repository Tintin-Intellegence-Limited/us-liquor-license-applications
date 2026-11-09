# New restaurant and bar liquor license applications (US, last 30 days)

A free, machine-readable list of restaurants and bars that recently filed for a liquor license in 22 US metros: New York City, Westchester, Long Island, the Hudson Valley, Albany-Capital Region, Rochester, Buffalo, Fairfield County CT, Los Angeles, Phoenix, the Chicago suburbs, Raleigh-Durham, Charlotte, Greensboro-Winston-Salem, Miami-Fort Lauderdale, Tampa Bay, Orlando and five Texas metros (Houston, Dallas-Fort Worth, Austin, San Antonio, Waco-Temple). A liquor license application is usually the earliest public sign that a new restaurant or bar is about to open, often weeks before it opens its doors.

This dataset is published by [PourWire](https://pourwire.com/?utm_source=github&utm_medium=dataset), which tracks these filings every day for insurance agents, POS resellers, equipment suppliers and food distributors who sell to new venues.

**Coverage:** 334 filings from 2026-10-10 to 2026-11-06.

| Metro | Filings | Live list (updated daily) |
|---|---|---|
| New York City | 52 | [pourwire.com/new-york/liquor-license-applications](https://pourwire.com/new-york/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Houston | 50 | [pourwire.com/houston/liquor-license-applications](https://pourwire.com/houston/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Los Angeles | 50 | [pourwire.com/los-angeles/liquor-license-applications](https://pourwire.com/los-angeles/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Dallas-Fort Worth | 37 | [pourwire.com/dallas-fort-worth/liquor-license-applications](https://pourwire.com/dallas-fort-worth/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Phoenix | 33 | [pourwire.com/phoenix/liquor-license-applications](https://pourwire.com/phoenix/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Fairfield County, CT | 28 | [pourwire.com/fairfield-ct/liquor-license-applications](https://pourwire.com/fairfield-ct/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Austin | 18 | [pourwire.com/austin/liquor-license-applications](https://pourwire.com/austin/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Long Island | 17 | [pourwire.com/long-island/liquor-license-applications](https://pourwire.com/long-island/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| San Antonio | 17 | [pourwire.com/san-antonio/liquor-license-applications](https://pourwire.com/san-antonio/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Hudson Valley | 8 | [pourwire.com/hudson-valley/liquor-license-applications](https://pourwire.com/hudson-valley/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Buffalo | 7 | [pourwire.com/buffalo/liquor-license-applications](https://pourwire.com/buffalo/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Rochester | 7 | [pourwire.com/rochester/liquor-license-applications](https://pourwire.com/rochester/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Waco-Temple | 5 | [pourwire.com/waco-temple/liquor-license-applications](https://pourwire.com/waco-temple/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Westchester | 3 | [pourwire.com/westchester/liquor-license-applications](https://pourwire.com/westchester/liquor-license-applications?utm_source=github&utm_medium=dataset) |
| Albany-Capital Region | 2 | [pourwire.com/capital-region/liquor-license-applications](https://pourwire.com/capital-region/liquor-license-applications?utm_source=github&utm_medium=dataset) |

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

`data/liquor-license-wait-times.csv`: how long restaurant and bar liquor license applications take in Texas, New York State (New York City plus Long Island, Westchester, Hudson Valley, Capital Region, Rochester and Buffalo) and Los Angeles (median days, sample size, as-of date, source guide). See the section below.

## Sources

Public records from the Texas Alcoholic Beverage Commission (TABC), the New York State Liquor Authority, NYC permit data, the California Department of Alcoholic Beverage Control, the Florida DBPR, and the state or local liquor licensing records for Arizona, the Chicago suburbs, North Carolina and Connecticut. Chains, hotels, gas stations, grocery and liquor stores are filtered out, so the list is mostly independent restaurants and bars.

## How long does a liquor license take?

PourWire also tracks how long these applications wait before the state acts on them. As of October 2026:

- **Texas (TABC):** median 24 days from application to issued license. [Texas TABC pending applications guide](https://pourwire.com/texas/tabc-pending-applications-guide?utm_source=github&utm_medium=dataset)
- **New York (SLA):** restaurant and bar applications pending a median of about 4 months (118 days) in New York City, a quarter over 212 days. Outside the city, as of November 2026: Westchester 121 days, Capital Region 119, Long Island 113, Hudson Valley 89, Buffalo 86, Rochester 83. [NY SLA pending applications guide](https://pourwire.com/new-york/sla-pending-applications-guide?utm_source=github&utm_medium=dataset)
- **California (ABC, Los Angeles):** median about 2 months (67 days) from application to issued license. [LA ABC pending applications guide](https://pourwire.com/los-angeles/abc-pending-applications-guide?utm_source=github&utm_medium=dataset)

Each guide also explains how to look up an application and what the license classes mean.

## Free JSON API

The same public list is available as JSON, no key or signup needed:

```
GET https://pourwire.com/api/public/openings?metro=new-york
```

- `metro` (required): one of `new-york`, `westchester`, `long-island`, `hudson-valley`, `capital-region`, `rochester`, `buffalo`, `fairfield-ct`, `los-angeles`, `phoenix`, `chicago-suburbs`, `raleigh`, `charlotte`, `greensboro`, `miami`, `tampa`, `orlando`, `houston`, `dallas-fort-worth`, `austin`, `san-antonio` or `waco-temple`
- `status` (optional): `new`, `in_buildout` or `approved`
- `limit` (optional): 1 to 200, default 100
- `ref` (optional): your app's name, added as `utm_source` on the returned links

Each opening has `business_name`, `legal_name`, `venue_type`, `street`, `city`, `zip`, `estimated_opening`, `status`, `confidence`, `first_filed`, a `filings` list (`source`, `type`, `date`, `license_type`) and a `page_url`. Responses are cached for an hour; please keep it to a few requests per metro per day.

## Want the full record?

The live lists on pourwire.com add the full address, license type, filing status and, where available, the owner contact, and they update every day. There is a free sample for every metro: [pourwire.com](https://pourwire.com/?utm_source=github&utm_medium=dataset).

## License

Data: [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/). Please credit "PourWire (pourwire.com)".

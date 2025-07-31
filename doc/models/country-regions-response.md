
# Country Regions Response

A list of country regions

## Structure

`CountryRegionsResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<CountryRegionSummary>`](../../doc/models/country-region-summary.md) | Optional | A list of RegionSummaries |

## Example (as JSON)

```json
{
  "data": [
    {
      "countryCode": "US",
      "fipsCode": "48",
      "isoCode": "TX",
      "name": "Texas",
      "wikiDataId": "Q1439"
    },
    {
      "countryCode": "US",
      "fipsCode": "39",
      "isoCode": "OH",
      "name": "Ohio",
      "wikiDataId": "Q1397"
    },
    {
      "countryCode": "US",
      "fipsCode": "31",
      "isoCode": "NE",
      "name": "Nebraska",
      "wikiDataId": "Q1553"
    },
    {
      "countryCode": "US",
      "fipsCode": "50",
      "isoCode": "VT",
      "name": "Vermont",
      "wikiDataId": "Q16551"
    },
    {
      "countryCode": "US",
      "fipsCode": "15",
      "isoCode": "HI",
      "name": "Hawaii",
      "wikiDataId": "Q782"
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/geo/countries/US/regions?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/geo/countries/US/regions?offset=0&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/geo/countries/US/regions?offset=10&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/geo/countries/US/regions?offset=55&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 5,
    "totalCount": 56
  },
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    },
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    },
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ]
}
```


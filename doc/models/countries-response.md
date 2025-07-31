
# Countries Response

A list of countries

## Structure

`CountriesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<CountrySummary>`](../../doc/models/country-summary.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "code": "SM",
      "currencyCodes": [
        "EUR"
      ],
      "name": "San Marino",
      "wikiDataId": "Q238"
    },
    {
      "code": "NE",
      "currencyCodes": [
        "XOF"
      ],
      "name": "Niger",
      "wikiDataId": "Q1032"
    },
    {
      "code": "MT",
      "currencyCodes": [
        "EUR"
      ],
      "name": "Malta",
      "wikiDataId": "Q233"
    },
    {
      "code": "KZ",
      "currencyCodes": [
        "KZT"
      ],
      "name": "Kazakhstan",
      "wikiDataId": "Q232"
    },
    {
      "code": "KE",
      "currencyCodes": [
        "KES"
      ],
      "name": "Kenya",
      "wikiDataId": "Q114"
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/geo/countries?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/geo/countries?offset=0&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/geo/countries?offset=10&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/geo/countries?offset=195&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 5,
    "totalCount": 198
  },
  "errors": [
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


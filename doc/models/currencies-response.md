
# Currencies Response

A list of currencies

## Structure

`CurrenciesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<Currency>`](../../doc/models/currency.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "code": "AWG",
      "countryCodes": [
        "AW"
      ],
      "symbol": "symbol2"
    },
    {
      "code": "AZN",
      "countryCodes": [
        "AZ"
      ],
      "symbol": "symbol2"
    },
    {
      "code": "BAM",
      "countryCodes": [
        "BA"
      ],
      "symbol": "symbol2"
    },
    {
      "code": "BBD",
      "countryCodes": [
        "BB"
      ],
      "symbol": "symbol2"
    },
    {
      "code": "BDT",
      "countryCodes": [
        "BD"
      ],
      "symbol": "symbol2"
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/locale/currencies?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/locale/currencies?offset=5&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/locale/currencies?offset=15&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/locale/currencies?offset=200&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 10,
    "totalCount": 205
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


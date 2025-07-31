
# Country Region Response

Country region details response

## Structure

`CountryRegionResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Data` | [`CountryRegionDetails`](../../doc/models/country-region-details.md) | Optional | Full country region details |

## Example (as JSON)

```json
{
  "data": {
    "capital": "Sacramento",
    "countryCode": "US",
    "fipsCode": "6",
    "isoCode": "CA",
    "name": "California",
    "numCities": 1532,
    "wikiDataId": "Q99"
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


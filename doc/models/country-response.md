
# Country Response

Country details response

## Structure

`CountryResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Data` | [`CountryDetails`](../../doc/models/country-details.md) | Optional | Full country details |

## Example (as JSON)

```json
{
  "data": {
    "callingCode": "+1",
    "code": "US",
    "currencyCodes": [
      "USD"
    ],
    "flagImageUri": "http://commons.wikimedia.org/wiki/Special:FilePath/Flag%20of%20the%20United%20States.svg",
    "name": "United States",
    "numRegions": 56,
    "wikiDataId": "Q30"
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


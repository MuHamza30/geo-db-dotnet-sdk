
# Country Details

Full country details

## Structure

`CountryDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CallingCode` | `string` | Optional | The country dialing prefix |
| `Code` | `string` | Optional | The ISO-3166 country code |
| `CurrencyCodes` | `List<string>` | Optional | A list of supported ISO-4217 currency codes |
| `FlagImageUri` | `string` | Optional | The country flag image |
| `Name` | `string` | Optional | The country name (varies by languageCode) |
| `NumRegions` | `int?` | Optional | The number of regions in this country |
| `WikiDataId` | `string` | Optional | The country WikiData id |

## Example (as JSON)

```json
{
  "callingCode": "+1",
  "code": "US",
  "currencyCodes": [
    "USD"
  ],
  "flagImageUri": "http://commons.wikimedia.org/wiki/Special:FilePath/Flag%20of%20the%20United%20States.svg",
  "name": "United States",
  "numRegions": 56,
  "wikiDataId": "Q30"
}
```


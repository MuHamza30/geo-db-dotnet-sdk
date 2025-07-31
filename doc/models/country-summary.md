
# Country Summary

Minimal country info

## Structure

`CountrySummary`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Code` | `string` | Optional | The ISO-3166 country code |
| `CurrencyCodes` | `List<string>` | Optional | A list of supported ISO-4217 currency codes |
| `Name` | `string` | Optional | The country name (varies by languageCode) |
| `WikiDataId` | `string` | Optional | The country WikiData id |

## Example (as JSON)

```json
{
  "code": "US",
  "currencyCodes": [
    "USD"
  ],
  "name": "United States",
  "wikiDataId": "Q30"
}
```



# Country Region Summary

Minimal country region info

## Structure

`CountryRegionSummary`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CountryCode` | `string` | Optional | An ISO-3166 country code |
| `FipsCode` | `string` | Optional | The FIPS 10-4 region code |
| `IsoCode` | `string` | Optional | The ISO region code |
| `Name` | `string` | Optional | The region name (varies by languageCode) |
| `WikiDataId` | `string` | Optional | The region WikiData id |

## Example (as JSON)

```json
{
  "countryCode": "US",
  "fipsCode": "6",
  "isoCode": "CA",
  "name": "California",
  "wikiDataId": "Q99"
}
```


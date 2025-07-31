
# Country Region Details

Full country region details

## Structure

`CountryRegionDetails`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Capital` | `string` | Optional | The region's capital city (varies by languageCode) |
| `CountryCode` | `string` | Optional | An ISO-3166 country code |
| `FipsCode` | `string` | Optional | The FIPS 10-4 region code |
| `IsoCode` | `string` | Optional | The ISO region code |
| `Name` | `string` | Optional | The region name (varies by languageCode) |
| `NumCities` | `int?` | Optional | The number of cities in this region |
| `WikiDataId` | `string` | Optional | The region WikiData id |

## Example (as JSON)

```json
{
  "capital": "Sacramento",
  "countryCode": "US",
  "fipsCode": "6",
  "isoCode": "CA",
  "name": "California",
  "numCities": 1532,
  "wikiDataId": "Q99"
}
```



# Populated Place Summary

Minimal populated-place info

## Structure

`PopulatedPlaceSummary`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Country` | `string` | Optional | The country name (varies by languageCode) |
| `CountryCode` | `string` | Optional | The ISO-3166 country code |
| `Distance` | `double?` | Optional | Included if this is the result of a distance query |
| `Id` | `int?` | Optional | The place GeoDB native id |
| `Latitude` | `double?` | Optional | The place latittude (-90.0 to 90.0) |
| `Longitude` | `double?` | Optional | The place longitude (-180.0 to 180.0) |
| `Name` | `string` | Optional | The place name (varies by languageCode) |
| `Population` | `int?` | Optional | The place population |
| `Region` | `string` | Optional | The region name (varies by languageCode) |
| `RegionCode` | `string` | Optional | The ISO or FIPS region code |
| `Type` | [`PopulatedPlaceTypeEnum?`](../../doc/models/populated-place-type-enum.md) | Optional | One of a set of enumerated populated-place types known by the service (currently only level-2 admin divisions and<br>cities) |
| `WikiDataId` | `string` | Optional | The place WikiData id |

## Example (as JSON)

```json
{
  "country": "United States of America",
  "countryCode": "US",
  "id": 123214,
  "latitude": 40.67,
  "longitude": -73.94,
  "name": "New York City",
  "region": "New York",
  "regionCode": "NY",
  "type": "CITY",
  "wikiDataId": "Q60",
  "distance": 57.2
}
```


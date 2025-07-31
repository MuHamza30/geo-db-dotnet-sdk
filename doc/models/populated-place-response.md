
# Populated Place Response

Populated-place details response

## Structure

`PopulatedPlaceResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Data` | [`PopulatedPlaceDetails`](../../doc/models/populated-place-details.md) | Optional | Full populated-place details |

## Example (as JSON)

```json
{
  "data": {
    "country": "United States of America",
    "countryCode": "US",
    "deleted": false,
    "elevationMeters": 10,
    "id": 123214,
    "latitude": 40.67,
    "longitude": -73.94,
    "name": "New York City",
    "population": 8398748,
    "region": "New York",
    "regionCode": "NY",
    "timezone": "America__New_York",
    "type": "CITY",
    "wikiDataId": "Q60"
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


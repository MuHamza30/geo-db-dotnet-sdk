
# Time Zone Response

A time-zone

## Structure

`TimeZoneResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Id` | `string` | Optional | The time-zone id |
| `Name` | `string` | Optional | The time-zone name |
| `RawUtcOffsetHours` | `int?` | Optional | The number of hours this time-zone is offset from UTC |

## Example (as JSON)

```json
{
  "data": {
    "id": "America__Marigot",
    "name": "Atlantic Standard Time",
    "rawUtcOffsetHours": -4
  },
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ],
  "id": "id8",
  "name": "name8",
  "rawUtcOffsetHours": 110
}
```


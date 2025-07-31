
# Distance Response

A decimal distance (in miles or kilometers)

## Structure

`DistanceResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Data` | `double?` | Optional | The distance in units as set by the distanceUnit param (defaults to miles) |

## Example (as JSON)

```json
{
  "data": 6707.9,
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    },
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


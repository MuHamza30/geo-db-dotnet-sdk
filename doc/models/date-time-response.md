
# Date Time Response

An ISO-6801 date-time response

## Structure

`DateTimeResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Data` | `DateTime?` | Optional | The date-time in ISO-6801 format: yyyyMMdd'T'HHmmssZ |

## Example (as JSON)

```json
{
  "data": "2020-10-05T01:16:53.504604+04:30",
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ]
}
```


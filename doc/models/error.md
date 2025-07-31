
# Error

An error that occurred processing the request

## Structure

`Error`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Code` | [`ErrorCodeEnum?`](../../doc/models/error-code-enum.md) | Optional | One of a set of enumerated error codes representing the types of errors that can occur processing a<br>request |
| `Message` | `string` | Optional | - |

## Example (as JSON)

```json
{
  "code": "ENTITY_NOT_FOUND",
  "message": "Param [someParam] has invalid value: invalidValue"
}
```


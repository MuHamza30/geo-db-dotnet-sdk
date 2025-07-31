
# Metadata

Result metadata (currently only associated with collection results)

## Structure

`Metadata`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `CurrentOffset` | `long?` | Optional | The zero-ary offset into the results (0 is the first result) |
| `TotalCount` | `long?` | Optional | The total number of results across pages |

## Example (as JSON)

```json
{
  "currentOffset": 0,
  "totalCount": 100
}
```


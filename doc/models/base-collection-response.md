
# Base Collection Response

Common properties for all collection  responses

## Structure

`BaseCollectionResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |

## Example (as JSON)

```json
{
  "links": [
    {
      "href": "/data/world/v1/some/resource?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/some/resource?offset=0&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/some/resource?offset=10&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/some/resource?offset=95&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 5,
    "totalCount": 100
  },
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ]
}
```



# Locales Response

A list of locales

## Structure

`LocalesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<Locale>`](../../doc/models/locale.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "code": "eu"
    },
    {
      "code": "ar_MR"
    },
    {
      "code": "es_DO"
    },
    {
      "code": "ru"
    },
    {
      "code": "az"
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/locale/locales?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/locale/locales?offset=45&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/locale/locales?offset=55&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/locale/locales?offset=770&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 50,
    "totalCount": 772
  },
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ]
}
```


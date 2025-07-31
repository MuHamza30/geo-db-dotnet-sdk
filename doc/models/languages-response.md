
# Languages Response

A list of languages supported by the system

## Structure

`LanguagesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<Language>`](../../doc/models/language.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "code": "fr",
      "name": "French"
    },
    {
      "code": "it",
      "name": "Italian"
    },
    {
      "code": "pt",
      "name": "Portuguese"
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/locale/languages?offset=0&limit=3",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/locale/languages?offset=0&limit=3",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/locale/languages?offset=6&limit=3",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/locale/languages?offset=6&limit=3",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 3,
    "totalCount": 8
  },
  "errors": [
    {
      "code": "PARAMS_MUTUALLY_EXCLUSIVE",
      "message": "message0"
    }
  ]
}
```


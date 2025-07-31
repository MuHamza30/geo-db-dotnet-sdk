
# Time Zones Response

A list of time-zones

## Structure

`TimeZonesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<TimeZone>`](../../doc/models/time-zone.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "id": "America__Marigot",
      "name": "Atlantic Standard Time",
      "rawUtcOffsetHours": -4
    },
    {
      "id": "Asia__Aqtau",
      "name": "West Kazakhstan Time",
      "rawUtcOffsetHours": 5
    },
    {
      "id": "Pacific__Kwajalein",
      "name": "Marshall Islands Time",
      "rawUtcOffsetHours": 12
    },
    {
      "id": "America__El_Salvador",
      "name": "Central Standard Time",
      "rawUtcOffsetHours": -6
    },
    {
      "id": "Asia__Pontianak",
      "name": "Western Indonesia Time",
      "rawUtcOffsetHours": 7
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/locale/timezones?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/locale/timezones?offset=0&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/locale/timezones?offset=10&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/locale/timezones?offset=595&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 5,
    "totalCount": 600
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


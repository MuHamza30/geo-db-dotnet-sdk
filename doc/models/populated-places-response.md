
# Populated Places Response

A list of populated places

## Structure

`PopulatedPlacesResponse`

## Fields

| Name | Type | Tags | Description |
|  --- | --- | --- | --- |
| `Errors` | [`List<Error>`](../../doc/models/error.md) | Optional | - |
| `Links` | [`List<Link>`](../../doc/models/link.md) | Optional | - |
| `Metadata` | [`Metadata`](../../doc/models/metadata.md) | Optional | Result metadata (currently only associated with collection results) |
| `Data` | [`List<PopulatedPlaceSummary>`](../../doc/models/populated-place-summary.md) | Optional | - |

## Example (as JSON)

```json
{
  "data": [
    {
      "country": "Andorra",
      "countryCode": "AD",
      "id": 2987553,
      "latitude": 42.57777778,
      "longitude": 1.61944444,
      "name": "L'Aldosa de Canillo",
      "region": "Canillo",
      "regionCode": "2",
      "type": "CITY",
      "wikiDataId": "Q24371",
      "distance": 246.8
    },
    {
      "country": "Andorra",
      "countryCode": "AD",
      "id": 3086756,
      "latitude": 42.57667,
      "longitude": 1.51773,
      "name": "La Cortinada",
      "region": "Ordino",
      "regionCode": "5",
      "type": "CITY",
      "wikiDataId": "Q24486",
      "distance": 246.8
    },
    {
      "country": "Andorra",
      "countryCode": "AD",
      "id": 3056764,
      "latitude": 42.4859,
      "longitude": 1.49045,
      "name": "La Margineda",
      "region": "Andorra la Vella",
      "regionCode": "7",
      "type": "CITY",
      "wikiDataId": "Q2536296",
      "distance": 246.8
    },
    {
      "country": "Andorra",
      "countryCode": "AD",
      "id": 978,
      "latitude": 42.544354,
      "longitude": 1.515427,
      "name": "La Massana",
      "region": "La Massana",
      "regionCode": "4",
      "type": "CITY",
      "wikiDataId": "Q3820973",
      "distance": 246.8
    },
    {
      "country": "Andorra",
      "countryCode": "AD",
      "id": 759,
      "latitude": 42.5,
      "longitude": 1.53333333,
      "name": "Les Escaldes",
      "region": "Escaldes-Engordany",
      "regionCode": "08",
      "type": "CITY",
      "wikiDataId": "Q1050185",
      "distance": 246.8
    }
  ],
  "links": [
    {
      "href": "/data/world/v1/geo/cities?offset=0&limit=5",
      "rel": "first"
    },
    {
      "href": "/data/world/v1/geo/cities?offset=0&limit=5",
      "rel": "prev"
    },
    {
      "href": "/data/world/v1/geo/cities?offset=10&limit=5",
      "rel": "next"
    },
    {
      "href": "/data/world/v1/geo/cities?offset=273685&limit=5",
      "rel": "last"
    }
  ],
  "metadata": {
    "currentOffset": 5,
    "totalCount": 273690
  },
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


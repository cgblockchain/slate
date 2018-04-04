# Draft



## Add Draft

```shell

 curl \
  -X POST \
  -H "Content-Type: application/json" \
  -d '{"NAME": "logbook", "MIXINS": [], "FIELDS": [{"NAME": "incident", "TYPE": "text"}]}' \
  https://compliance-guard.lan/api/v1/drafts

```

> The above command returns JSON structured like this:

```json

  {
    "status": "success",
    "data": {
      "draft": {
        "id": "6a2017db-6f7c-45e8-ab28-ebe9e589b4b3"
        "name": "logbook",
        "mixins": [],
        "fields": [
          {
            "type": "text",
            "name": "incident"
          }
        ]
      }
    }
  }

```

Use this method to construct new Entities or new versions of an Entity.

### HTTP Request

`POST /api/v1/drafts`

### Payload Attributes

| Attribute | Description |
|-----------|--------|-------------|
| NAME     | String | Name of the draft      |
| MIXINS     | String[] | Array of used mixins      |
| FIELDS     | String[] | Array of fields, which entries of this type will have      |




## Get Draft

```shell

 curl \
   -X GET \
   https://compliance-guard.lan/api/v1/drafts/6a2017db-6f7c-45e8-ab28-ebe9e589b4b3

```

> The above command returns JSON structured like this:

```json

  {
    "status": "success",
    "data": {
      "draft": {
        "id": "6a2017db-6f7c-45e8-ab28-ebe9e589b4b3",
        "name": "logbook",
        "mixins": [],
        "fields": [
          {
            "type": "text",
            "name": "incident"
          }
        ]
      }
    }
  }

```

Use this method to get the information about a Draft.

### HTTP Request

`GET /api/v1/drafts/<id>`

### URL Parameters

| Parameter | Type   | Description |
|-----------|--------|-------------|
| id     | String | ID of the desired draft      |





## Get list of Drafts

```shell

 curl \
   -X GET \
   https://compliance-guard.lan/api/v1/entities?name=logbook&limit=5

```

> The above command returns JSON structured like this:

```json

  {
    "status": "success",
    "data": {
      "drafts": [
        {
          "id": "6a2017db-6f7c-45e8-ab28-ebe9e589b4b3",
          "name": "logbook",
          "mixins": [],
          "fields": [
            {
              "type": "text",
              "name": "incident"
            }
          ]
        }
      ]
    }
  }

```

This endpoint returns a list of all the current Drafts.

### HTTP Request

`GET /api/v1/drafts`

### URL Parameters

| Parameter | Type   | Description |
|-----------|--------|-------------|
| name     | String | [Optional] Name of the desired draft      |
| limit     | String | [Optional] Limit of number of fetched drafts. Default value: 0      |
| offset     | String | [Optional] Number of drafts to skip. Default value: 5      |




## Update Draft

```shell

 curl \
   -X PUT \
   -H "Content-Type: application/json" \
   -d '{"name": "logbook", "mixins": [], "fields": [{"name": "timestamp", "type": "date"}]}' \
   https://compliance-guard.lan/api/v1/drafts/6a2017db-6f7c-45e8-ab28-ebe9e589b4b3

```

> The above command returns JSON structured like this:

```json

  {
    "status": "success",
    "data": {
      "draft": {
        "id": "6a2017db-6f7c-45e8-ab28-ebe9e589b4b3",
        "name": "logbook",
        "mixins": [],
        "fields": [
          {
            "type": "date",
            "name": "timestamp"
          }
        ]
      }
    }
  }

```

Use this method to update a Draft.

### HTTP Request

`PUT /api/v1/drafts/<id>`

### URL Parameters

| Parameter | Type   | Description |
|-----------|--------|-------------|
| id     | String | ID of the desired draft      |
| name     | String | [Optional] New name of the draft      |
| mixins     | String[] | [Optional] New array of used mixins      |
| fields     | String[] | [Optional] New array of fields, which entries of this type will have      |




## Delete Draft

```shell

 curl \
   -X DELETE \
   https://compliance-guard.lan/api/v1/drafts/6a2017db-6f7c-45e8-ab28-ebe9e589b4b3

```

> The above command returns JSON structured like this:

```json

  {
    "status": "success",
    "data": null
  }

```

Use this method to delete a Draft.

### HTTP Request

`DELETE /api/v1/drafts/<id>`

### URL Parameters

| Parameter | Type   | Description |
|-----------|--------|-------------|
| ID     | String | of the desired draft      |




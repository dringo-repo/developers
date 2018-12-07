# Receipts

Receipts are records the report on the progress of a change requested during a [batch user upload](#batch-users). Each receipt will have a status value:

Status | Description
--------- | ---------
pending | The requested changes have not yet been processed
completed | The requested changed were made successfully
failed | The requested changed were made successfully

## Get All Receipts

```shell
curl -X GET 'https://example.dringo.io/api/receipts?ids=1,2'
  -H 'Authorization: Token token=meowmeowmeow'
```

> The above command returns JSON structured like this:

```json
{
  "receipts": [
    {
      "id": 1,
      "status": "pending",
      "errors": [],
      "links": {
        "receipt": "https://example.dringo.io/api/receipts/1",
        "user": null
      }
    },
    {
      "id": 2,
      "status": "failed",
      "errors": ["Email can't be blank"],
      "links": {
        "receipt": "https://example.dringo.io/api/receipts/2",
        "user": null
      }
    }
  ]
}
```

This endpoint retrieves all receipts.

### HTTP Request

`GET https://example.dringo.io/api/receipts?updated_at=1544135037&ids=<ids>`

### Query Parameters

Parameter | Default | Description
--------- | --------- | ---------
ids | null | A comma delaminated list of receipt ids (no spaces) which will limit results to only those ids.

<aside class="success">
Remember — a happy receipt is an authenticated receipt!
</aside>

## Get a Specific Receipt

```shell
curl -X GET 'https://example.dringo.io/api/receipts/2'
  -H 'Authorization: Token token=meowmeowmeow'
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "status": "failed",
  "errors": ["Email can't be blank"],
  "links": {
    "receipt": "https://example.dringo.io/api/receipts/2",
    "user": null
  }
}
```

This endpoint retrieves a specific receipt.

### HTTP Request

`GET https://example.dringo.io/api/receipts/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID of the receipt to retrieve

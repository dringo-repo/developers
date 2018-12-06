# Receipts

## Get All Receipts

```shell
curl 'https://example.dringo.io/api/receipts'
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
    }
  ]
}
```

This endpoint retrieves all receipts.

### HTTP Request

`GET https://example.dringo.io/api/receipts?updated_at=1544135037&ids=1,2,3`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
ids | null | A comma delaminated list of receipt ids (no spaces) which will limit results to only those ids.

<aside class="success">
Remember — a happy receipt is an authenticated receipt!
</aside>

## Get a Specific Receipt

```shell
curl "https://example.dringo.io/api/receipts/2"
  -H "Authorization: Token token=meowmeowmeow"
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

# Batch Users

## Submitting a batch of changes

```shell
curl "https://example.dringo.io/api/users/batch/update_or_create"
  -H "Authorization: Token token=meowmeowmeow"
  -D '{
        changes: [
          { "id": 1, "first_name": "Fresh", last_name: "Prince" },
          { "first_name": "Carlton", last_name: "Banks" },
        ]
      }'
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
      "status": "pending",
      "errors": [],
      "links": {
        "receipt": "https://example.dringo.io/api/receipts/2",
        "user": null
      }
    }
  ]
}
```

This endpoint retrieves a specific receipt.

### HTTP Request

`POST https://example.dringo.io/api/users/batch/update_or_create`

### POST Data

Parameter | Description
--------- | -----------
changes | Array of JSON objects containing changes to be implemented.

#### Change objects

Field | Type |Description
--------- | ----------- | -----------
id | Integer | ID of the user to update. If left blank, Dringo will attempt to create a user.
first_name | String | First name of user
last_name | String | Last name of user
emails | Array | List of email objects
national_admin | Boolean | If true, the user will have national admin privileges
chapter_admin | Boolean | If true, the user will have chapter admin privileges
chapter_name | String | Name of the user's chapter
university_name | String | Name of the user's university
alumni | Boolean | If true, the user will be marked as an alumni
graduation_year | String | Graduation year of the user, must be 4 characters
experiences | Array | List of experience objects

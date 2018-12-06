# Users

## Get All Kittens

```shell
curl 'https://example.dringo.io/api/users'
  -H 'Authorization: Token token=meowmeowmeow'
```

> The above command returns JSON structured like this:

```json
{
  "users": [
    {
      "id": 2,
      "first_name": "Will",
      "last_name": "Smith",
      "updated_at": 1540662498,
      "created_at": 1540662498,
      "emails": [
        { "value": "will@smith.co", "primary": true },
        { "value": "prince@ofbelair.co", "primary": false }
      ],
      "national_admin": false,
      "chapter_admin": false,
      "chapter_name": "alpha beta",
      "university_name": "University of California, Berkley",
      "alumni": true,
      "graduation_year": "1986",
      "experiences": [
        {
          "company": "General Mills",
          "title": "null",
          "start": null,
          "end": null
        }
      ],
    }
  ]
}
```

This endpoint retrieves all users.

### HTTP Request

`GET https://example.dringo.io/api/users`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
include_cats | false | If set to true, the result will also include cats.
available | true | If set to false, the result will include users that have already been adopted.

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

## Get a Specific Kitten

```shell
curl "https://example.dringo.io/api/users/2"
  -H "Authorization: Token token=meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "name": "Max",
  "breed": "unknown",
  "fluffiness": 5,
  "cuteness": 10
}
```

This endpoint retrieves a specific user.

<aside class="warning">Inside HTML code blocks like this one, you can't use Markdown, so use <code>&lt;code&gt;</code> blocks to denote code.</aside>

### HTTP Request

`GET https://example.dringo.io/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to retrieve

## Delete a Specific Kitten

```shell
curl "https://example.dringo.io/api/users/2"
  -X DELETE
  -H "Authorization: Token token=meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 2,
  "deleted" : ":("
}
```

This endpoint deletes a specific user.

### HTTP Request

`DELETE https://example.dringo.io/api/users/<ID>`

### URL Parameters

Parameter | Description
--------- | -----------
ID | The ID of the user to delete

# Users

## Get All Users

```shell
curl 'https://example.dringo.io/api/users'
  -H 'Authorization: Token token=meowmeowmeow'
```

> The above command returns JSON structured like this:

```json
{
  "users": [
    {
      "id": 1,
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

`GET https://example.dringo.io/api/users?updated_at=1544135037&ids=1,2,3`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
updated_at | null | Specify a [Unix Epoch timestamp](https://en.wikipedia.org/wiki/Unix_time) to only return users updated after that timestamp.
ids | null | A comma delaminated list of user ids (no spaces) which will limit results to only those ids.

<aside class="success">
Remember — a happy user is an authenticated user!
</aside>

## Get a Specific User

```shell
curl "https://example.dringo.io/api/users/2"
  -H "Authorization: Token token=meowmeowmeow"
```

> The above command returns JSON structured like this:

```json
{
  "id": 1,
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
```

This endpoint retrieves a specific user.

### HTTP Request

`GET https://example.dringo.io/api/users/<id>`

### URL Parameters

Parameter | Description
--------- | -----------
id | The ID of the user to retrieve

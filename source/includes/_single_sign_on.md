# User Single Sign On

You can use the Dringo API to generate Single Sign On Links for your user. This could allow you automatically log your users into Dringo from your organization's web portal.

## Generate a single sign on link

```shell
curl -X GET 'https://example.dringo.io//api/users/autologins'
  -H 'Authorization: Token token=meowmeowmeow'
  - D '{
         "id": 1
       }'
```

> The above command returns JSON structured like this:

```json
{
  "autologin_url": "https://example.dringo.io//user/autologin?temporary_token=xyz",
}
```

This endpoint will generate temporary single sign on link for the user associated with the id provided in the request.

<aside class="notice">
These single sign on links will expire after the first use or if another is generated.
</aside>

### HTTP Request

`GET https://example.dringo.io//api/users/autologins`

### Data Parameters

Parameter | Default | Description
--------- | --------- | ---------
id | null | The id of the user you want to generate a single sign on link for.

# User Single Sign On (SSO)

You can use the Dringo API to generate SSO links for your users. This allows you to dynamically provide automatic login links which can be used in your organization's web portal.

## Generate an SSO link

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

This endpoint will generate a temporary SSO link for the user associated with the id provided in the request.

<aside class="notice">
These SSO links will expire after first use or if another is generated.
</aside>

### HTTP Request

`GET https://example.dringo.io//api/users/autologins`

### Data Parameters

Parameter | Default | Description
--------- | --------- | ---------
id | null | The id of the user you want to generate an SSO link for

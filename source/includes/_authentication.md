# API Authentication

> To authorize, use this code:

```shell
# With shell, you can just pass the correct header with each request
curl 'api_endpoint_here'
  -H 'Authorization: Token token=meowmeowmeow'
```

> Make sure to replace `meowmeowmeow` with your API key.

Dringo uses API keys to allow access to the API. You can find your organization's API key at your admin dashboard.

Dringo expects for the API key to be included in all API requests to the server in a header that looks like the following:

`Authorization: Token token=meowmeowmeow`

<aside class="notice">
You must replace <code>meowmeowmeow</code> with your personal API key.
</aside>

# Handling errors

API clients must expect and gracefully handle transient errors, such as rate limiting or server errors. We recommend baking 5xx and 429 response handling into your low-level HTTP client so your integration can handle most errors automatically.

## Rate limiting (429 Too Many Requests)

```shell
# With shell, you can just pass the correct header with each request
curl 'api_endpoint_here' -I
  -H 'Authorization: Token token=meowmeowmeow'

# Result of to many requests
HTTP/1.1 429 Too Many Requests
RateLimit-Limit: 1
RateLimit-Remaining: 0
RateLimit-Reset: 1544130240
```

You can perform up to 60 requests per 1-minute period from the same IP address. If you exceed this limit, you'll get a [429 Too Many Requests](http://tools.ietf.org/html/draft-nottingham-http-new-status-02#section-4) response for subsequent requests. Check the `RateLimit-Reset` header to see how many seconds to wait before retrying the request.

## 5xx Server Error

If Dringo is having trouble, you will get a response with a 5xx status code indicating a server error.

[list of 5xx server errors](https://en.wikipedia.org/wiki/List_of_HTTP_status_codes#5xx_Server_errors)

## 404 Not Found

API requests may 404 due to deleted or missing content.

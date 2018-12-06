# Pagination

``` shell
curl 'https://example.dringo.io/api/users?page=2&per_page=100'
```

Most collection APIs paginate their results and will be paginated to 30 items by default.  For some resources, you can also set a custom page size up to 100 with the `?per_page` parameter.

## Link Header

The Dringo API follows the [RFC5988 convention](https://tools.ietf.org/html/rfc5988) of using the `Link` header to provide URLs for the `next` page. Follow this convention to retrieve the next page of data—please don't build the pagination URLs yourself!

```
Link: <https://example.dringo.io/api/users?page=15>; rel="next",
  <https://example.dringo.io/api/users?page=34>; rel="last",
  <https://example.dringo.io/api/users?page=1>; rel="first",
  <https://example.dringo.io/api/users?page=13>; rel="prev"
```

The possible `rel` values are:

Name | Description
-----------|-----------|
`next` |The link relation for the immediate next page of results.
`last` |The link relation for the last page of results.
`first` |The link relation for the first page of results.
`prev` |The link relation for the immediate previous page of results.

If the `Link` header is blank, that's the last page. The Dringo API also provides the `X-Total-Count` header, which displays the total number of resources in the collection you are fetching.

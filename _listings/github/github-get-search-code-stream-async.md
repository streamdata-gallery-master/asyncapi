---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/search/code
  scheme: https
  asyncapi_servers_variables:
    order:
      description: The sort field. if sort param is provided. Can be either asc or
        desc.
    q:
      description: |
        The search terms. This can be any combination of the supported code
        search parameters:
        'Search In' Qualifies which fields are searched. With this qualifier
        you can restrict the search to just the file contents, the file path,
        or both.
        'Languages' Searches code based on the language it's written in.
        'Forks' Filters repositories based on the number of forks, and/or
        whether code from forked repositories should be included in the results
        at all.
        'Size' Finds files that match a certain size (in bytes).
        'Path' Specifies the path that the resulting file must be at.
        'Extension' Matches files with a certain extension.
        'Users' or 'Repositories' Limits searches to a specific user or repository.
    sort:
      description: |
        Can only be 'indexed', which indicates how recently a file has been indexed
        by the GitHub search infrastructure. If not provided, results are sorted
        by best match.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search_code'
---
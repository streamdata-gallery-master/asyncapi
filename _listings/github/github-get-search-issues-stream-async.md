---
version: 1.2.0
x-collection-name: GitHub Get Search Issues (stream)
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/search/issues
  scheme: https
  asyncapi_servers_variables:
    order:
      description: The sort field. if sort param is provided. Can be either asc or
        desc.
    q:
      description: 'The q search term can also contain any combination of the supported
        issue search qualifiers:'
    sort:
      description: 'The sort field. Can be comments, created, or updated. Default:
        results are sorted by best match.'
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search_issues'
---
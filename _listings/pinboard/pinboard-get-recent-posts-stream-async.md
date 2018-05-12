---
version: 1.2.0
x-collection-name: Pinboard
info:
  title: Pinboard
  version: 1.2.0
servers:
- url: api.pinboard.in/posts/recent
  scheme: https
  asyncapi_servers_variables:
    tag:
      description: filter by up to three tags
    count:
      description: number of results to return. Default is 15, max is 100
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/posts_recent'
---
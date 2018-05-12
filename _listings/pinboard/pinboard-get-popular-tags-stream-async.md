---
version: 1.2.0
info:
  title: Pinboard
  version: 1.2.0
servers:
- url: api.pinboard.in/posts/suggest
  scheme: https
  asyncapi_servers_variables:
    url:
      description: url to suggest from.
    format:
      description: the format to return
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/posts_suggest'
---
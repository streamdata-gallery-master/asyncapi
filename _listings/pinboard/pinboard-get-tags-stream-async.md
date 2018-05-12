---
version: 1.2.0
x-collection-name: Pinboard Get Tags (stream)
info:
  title: Pinboard
  version: 1.2.0
servers:
- url: api.pinboard.in/tags/get
  scheme: https
  asyncapi_servers_variables:
    format:
      description: the format to return
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/tags_get'
---
---
version: 1.2.0
x-collection-name: Instagram
info:
  title: Instagram
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;instagram-media-id&#125;/comments
  scheme: https
  asyncapi_servers_variables:
    100:
      description: Invalid parameter
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;instagram-media-id_#125;_comments'
---
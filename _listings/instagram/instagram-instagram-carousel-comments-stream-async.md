---
version: 1.2.0
info:
  title: Instagram
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;instagram-carousel-id&#125;/comments
  scheme: https
  asyncapi_servers_variables:
    100:
      description: Invalid parameter
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;instagram-carousel-id_#125;_comments'
---
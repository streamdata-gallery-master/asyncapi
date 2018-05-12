---
version: 1.2.0
x-collection-name: Facebook
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;user-id&#125;/photos
  scheme: https
  asyncapi_servers_variables:
    100:
      description: Invalid parameter
    200:
      description: Permissions error
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;user-id_#125;_photos'
---
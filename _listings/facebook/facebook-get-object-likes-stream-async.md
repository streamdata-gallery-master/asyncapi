---
version: 1.2.0
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;object-id&#125;/likes
  scheme: https
  asyncapi_servers_variables:
    total_count:
      description: Total number of User and Page likes on the object. To have this
        field returned, you must include the summary=true parameter and value in your
        request.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;object-id_#125;_likes'
---
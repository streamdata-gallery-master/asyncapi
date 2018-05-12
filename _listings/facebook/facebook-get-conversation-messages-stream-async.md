---
version: 1.2.0
x-collection-name: Facebook Get Conversation Messages (stream)
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;conversation-id&#125;/messages
  scheme: https
  asyncapi_servers_variables:
    Vector:
      description: Vector
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;conversation-id_#125;_messages'
---
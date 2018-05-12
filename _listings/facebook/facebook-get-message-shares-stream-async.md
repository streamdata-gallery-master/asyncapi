---
version: 1.2.0
x-collection-name: Facebook Get Message Shares (stream)
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;message-id&#125;/shares
  scheme: https
  asyncapi_servers_variables:
    description:
      description: The description of the shared item.
    link:
      description: The URL to the shared item.
    id:
      description: The shared item ID.
    name:
      description: The title of the shared item.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;message-id_#125;_shares'
---
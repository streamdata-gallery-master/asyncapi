---
version: 1.2.0
x-collection-name: Facebook
info:
  title: Facebook Get User Conversations (stream)
  version: 1.2.0
  description: This is a streaming API that has been autogenerated from the Facebook
    using Streamdata.io.
servers:
- url: graph.facebook.com/&#123;user-id&#125;/conversations
  scheme: https
  asyncapi_servers_variables:
    200:
      description: Permissions error
    100:
      description: Invalid parameter
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;user-id_#125;_conversations'
---
---
version: 1.2.0
x-collection-name: Box Pending Collaborations (stream)
info:
  title: Box
  version: 1.2.0
servers:
- url: api.box.com/collaborations
  scheme: https
  asyncapi_servers_variables:
    fields:
      description: Attribute(s) to include in the response
    status:
      description: Must be 'pending'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/collaborations'
---
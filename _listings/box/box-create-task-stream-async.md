---
version: 1.2.0
x-collection-name: Box
info:
  title: Box
  version: 1.2.0
servers:
- url: api.box.com/tasks
  scheme: https
  asyncapi_servers_variables:
    body:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/tasks'
---
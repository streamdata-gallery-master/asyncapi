---
version: 1.2.0
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/alerts
  scheme: https
  asyncapi_servers_variables:
    body:
      description: ""
    Authorization:
      description: ""
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/alerts'
---
---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/rate_limit
  scheme: https
  asyncapi_servers_variables:
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/rate_limit'
---
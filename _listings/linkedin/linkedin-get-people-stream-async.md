---
version: 1.2.0
info:
  title: LinkedIn
  version: 1.2.0
servers:
- url: api.linkedin.com/people/~
  scheme: https
  asyncapi_servers_variables:
    format:
      description: The message format
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/people_~'
---
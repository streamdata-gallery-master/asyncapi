---
version: 1.2.0
x-collection-name: LinkedIn Get Companies Updates (stream)
info:
  title: LinkedIn
  version: 1.2.0
servers:
- url: api.linkedin.com/companies/{id}/updates
  scheme: https
  asyncapi_servers_variables:
    format:
      description: The message format
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/companies_{id}_updates'
---
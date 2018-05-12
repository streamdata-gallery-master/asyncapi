---
version: 1.2.0
info:
  title: 1Forge
  version: 1.2.0
  description: ~
servers:
- url: forex.1forge.com/quotes
  scheme: https
  description: ~
  schemeVersion: ""
  asyncapi_servers_variables:
    pairs:
      description: A currency pair
    api_key:
      description: The api key.
    format:
      description: The format to return.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/?????'
  - $ref: '#/components/messages/quotes'
---
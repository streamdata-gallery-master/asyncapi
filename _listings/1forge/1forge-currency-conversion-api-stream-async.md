---
version: 1.2.0
info:
  title: 1Forge
  version: 1.2.0
  description: ~
servers:
- url: forex.1forge.com/convert
  scheme: https
  description: ~
  schemeVersion: ""
  asyncapi_servers_variables:
    api_key:
      description: The api key.
    from:
      description: Currency to convert from.
    to:
      description: Currency to convert to.
    quantity:
      description: The amount to convert.
    format:
      description: The format to return.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/?????'
  - $ref: '#/components/messages/convert'
---
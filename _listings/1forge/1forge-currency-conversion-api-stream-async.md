---
version: 1.2.0
x-collection-name: 1Forge
info:
  title: 1Forge Currency Conversion API (stream)
  version: 1.2.0
servers:
- url: forex.1forge.com/convert
  scheme: https
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
  - $ref: '#/components/messages/convert'
---
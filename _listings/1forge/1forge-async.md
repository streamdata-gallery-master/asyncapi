---
version: 1.2.0
info:
  title: 1Forge
  version: 1.2.0
servers:
- url: forex.1forge.com/quotes
  scheme: https
  asyncapi_servers_variables:
    pairs:
      description: A currency pair
    api_key:
      description: The api key.
    format:
      description: The format to return.
- url: forex.1forge.com/symbols
  scheme: https
  asyncapi_servers_variables:
    api_key:
      description: The api key.
    format:
      description: The format to return.
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
- url: forex.1forge.com/market_status
  scheme: https
  asyncapi_servers_variables:
    api_key:
      description: The api key.
    format:
      description: The format to return.
- url: forex.1forge.com/quota
  scheme: https
  asyncapi_servers_variables:
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
---
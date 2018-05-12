---
version: ""
x-collection-name: 1Forge Financial Market Status API (stream)
info:
  title: 1Forge Financial Market Status API (stream)
  version: 1.2.0
servers:
- url: forex.1forge.com/market_status
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
  - $ref: '#/components/messages/market_status'
---
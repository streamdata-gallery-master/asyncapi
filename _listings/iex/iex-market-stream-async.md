---
version: 1.2.0
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/market
  scheme: https
  asyncapi_servers_variables:
    format:
      description: ' Parameter is optional Value can only be csv When parameter is
        not present, format defaults to JSON'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/market'
---
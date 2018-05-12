---
version: 1.2.0
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stock/{symbol}/delayed-quote
  scheme: https
  asyncapi_servers_variables:
    symbol:
      description: Stock ticker symbol.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stock_{symbol}_delayed-quote'
---
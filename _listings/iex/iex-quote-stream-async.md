---
version: 1.2.0
x-collection-name: IEX Quote (stream)
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stock/{symbol}/quote
  scheme: https
  asyncapi_servers_variables:
    displayPercent:
      description: ' Optional If set to true, all percentage values will be multiplied
        by a factor of 100 (Ex: /stock/aapl/quote?displayPercent=true)'
    symbol:
      description: Stock ticker symbol.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stock_{symbol}_quote'
---
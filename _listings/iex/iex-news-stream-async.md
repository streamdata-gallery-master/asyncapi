---
version: 1.2.0
x-collection-name: IEX
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stock/{symbol}/news/last/{range}
  scheme: https
  asyncapi_servers_variables:
    symbol:
      description: Stock ticker symbol.
    range:
      description: The date range.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stock_{symbol}_news_last_{range}'
---
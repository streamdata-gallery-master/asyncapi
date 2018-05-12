---
version: 1.2.0
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stock/{symbol}/short-interest
  scheme: https
  asyncapi_servers_variables:
    format:
      description: ' Parameter is optional Value can be csv or psv When parameter
        is not present, format defaults to JSON'
    token:
      description: ' Parameter is optional Value is the API token from your IEX user
        account If you have been permissioned for CUSIP information you&rsquo;ll receive
        a CUSIP field, othewise data defaults to exclude CUSIP.'
    symbol:
      description: Stock ticker symbol.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stock_{symbol}_short-interest'
---
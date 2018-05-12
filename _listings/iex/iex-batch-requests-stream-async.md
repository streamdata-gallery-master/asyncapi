---
version: 1.2.0
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stock/market/batch
  scheme: https
  asyncapi_servers_variables:
    types:
      description: ' Required  Comma delimited list of endpoints to call. The names
        should match the individual endpoint names.  Limited to 10 types.'
    symbols:
      description: ' Optional  Comma delimited list of symbols limited to 100.  This
        parameter is used only if market option is used .'
    range:
      description: ' Optional  Used to specify a chart range if chart is used in types
        parameter.'
    "":
      description: ' Optional  Parameters that are sent to individual endpoints can
        be specified in batch calls and will be applied to each supporting endpoint.'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stock_market_batch'
---
---
version: 1.2.0
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/hist
  scheme: https
  asyncapi_servers_variables:
    date:
      description: ' Parameter is optional Value needs to be in four-digit year, two-digit
        month, two-digit day format (YYYYMMDD) (i.e May 15, 2017 would be written
        as 20170515) When parameter is not present, request returns all available
        dates'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/hist'
---
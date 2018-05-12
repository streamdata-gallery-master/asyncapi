---
version: 1.2.0
x-collection-name: IEX Historical Summary (stream)
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/stats/historical
  scheme: https
  asyncapi_servers_variables:
    date:
      description: ' Parameter is optional Value needs to be in four-digit year, two-digit
        month format (YYYYMM) (i.e January 2017 would be written as 201701) Historical
        data is only available for prior months, starting with January 2014 When parameter
        is not present, request returns prior month&rsquo;s data'
    format:
      description: ' Parameter is optional Value can only be csv When parameter is
        not present, format defaults to JSON'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stats_historical'
---
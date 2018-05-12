---
version: 1.2.0
x-collection-name: IEX TOPS (stream)
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/tops
  scheme: https
  asyncapi_servers_variables:
    symbols:
      description: ' Parameter is optional Value needs to be a comma-separated list
        of symbols (i.e SNAP,fb) When parameter is not present, request returns all
        symbols'
    format:
      description: ' Parameter is optional Value can only be csv When parameter is
        not present, format defaults to JSON'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/tops'
---
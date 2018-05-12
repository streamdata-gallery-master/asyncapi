---
version: 1.2.0
x-collection-name: IEX Book (stream)
info:
  title: IEX Trading API
  version: 1.2.0
servers:
- url: api.iextrading.com/deep/book
  scheme: https
  asyncapi_servers_variables:
    symbols:
      description: ' Parameter is required Value needs to be a comma-separated list
        of symbols (i.e SNAP,fb) Maximum of 10 symbols'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/deep_book'
---
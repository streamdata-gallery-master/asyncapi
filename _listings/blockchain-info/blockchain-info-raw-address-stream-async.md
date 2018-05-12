---
version: 1.2.0
x-collection-name: Blockchain Info Raw Address (stream)
info:
  title: Blockchain Info
  version: 1.2.0
servers:
- url: blockchain.info/rawaddr/{bitcoin_address}
  scheme: https
  asyncapi_servers_variables:
    bitcoin_address:
      description: The bitcoin address.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/rawaddr_{bitcoin_address}'
---
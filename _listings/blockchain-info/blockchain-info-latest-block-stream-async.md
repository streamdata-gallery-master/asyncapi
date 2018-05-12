---
version: 1.2.0
x-collection-name: Blockchain Info
info:
  title: Blockchain Info
  version: 1.2.0
servers:
- url: blockchain.info/latestblock
  scheme: https
  asyncapi_servers_variables:
    format:
      description: The format to return (json,html).
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/latestblock'
---
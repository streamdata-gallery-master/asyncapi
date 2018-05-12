---
version: 1.2.0
x-collection-name: Blockchain Info Blocks by Pool (stream)
info:
  title: Blockchain Info
  version: 1.2.0
servers:
- url: blockchain.info/blocks/{pool_name}
  scheme: https
  asyncapi_servers_variables:
    format:
      description: The format to return (json,html).
    pool_name:
      description: The pool name.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/blocks_{pool_name}'
---
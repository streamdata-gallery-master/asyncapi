---
version: ""
x-collection-name: 1Forge API Usage Quota API (stream)
info:
  title: 1Forge API Usage Quota API (stream)
  version: 1.2.0
servers:
- url: forex.1forge.com/quota
  scheme: https
  asyncapi_servers_variables:
    api_key:
      description: The api key.
    format:
      description: The format to return.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/quota'
---
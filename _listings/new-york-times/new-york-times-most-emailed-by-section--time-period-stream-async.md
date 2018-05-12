---
version: 1.2.0
x-collection-name: New York Times
info:
  title: New York Times
  version: 1.2.0
servers:
- url: api.nytimes.com/mostpopular/v2/mostemailed/{section}/{time-period}.json
  scheme: https
  asyncapi_servers_variables:
    section:
      description: The section of the paper.
    time-period:
      description: The period of time.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/mostpopular_v2_mostemailed_{section}_{time-period}_json'
---
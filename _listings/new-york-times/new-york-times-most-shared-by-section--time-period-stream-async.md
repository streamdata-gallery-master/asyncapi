---
version: 1.2.0
info:
  title: New York Times
  version: 1.2.0
servers:
- url: api.nytimes.com/mostpopular/v2/mostshared/{section}/{time-period}.json
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
  - $ref: '#/components/messages/mostpopular_v2_mostshared_{section}_{time-period}_json'
---
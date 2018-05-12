---
version: 1.2.0
x-collection-name: Meetup Categories (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/categories
  scheme: https
  asyncapi_servers_variables:
    fields:
      description: Parameter for requesting optional response properties
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_categories'
---
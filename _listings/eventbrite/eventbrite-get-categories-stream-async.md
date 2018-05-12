---
version: 1.2.0
x-collection-name: Eventbrite
info:
  title: Eventbrite
  version: 1.2.0
servers:
- url: www.eventbriteapi.com/categories/
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/categories_'
---
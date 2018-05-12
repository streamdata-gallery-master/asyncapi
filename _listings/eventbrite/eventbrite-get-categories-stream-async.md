---
version: 1.2.0
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
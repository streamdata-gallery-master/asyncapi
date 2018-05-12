---
version: 1.2.0
info:
  title: The Guardian
  version: 1.2.0
servers:
- url: content.guardianapis.com/search
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search'
---
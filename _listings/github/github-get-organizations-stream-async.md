---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/organizations
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/organizations'
---
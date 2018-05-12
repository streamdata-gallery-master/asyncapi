---
version: 1.2.0
x-collection-name: Twitter
info:
  title: Twitter
  version: 1.2.0
servers:
- url: api.twitter.com/trends/available.json
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/trends_available_json'
---
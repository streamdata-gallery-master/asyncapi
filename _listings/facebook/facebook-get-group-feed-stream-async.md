---
version: 1.2.0
x-collection-name: Facebook Get Group Feed (stream)
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;group-id&#125;/feed
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;group-id_#125;_feed'
---
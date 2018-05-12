---
version: 1.2.0
x-collection-name: Facebook
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;album-id&#125;/photos
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;album-id_#125;_photos'
---
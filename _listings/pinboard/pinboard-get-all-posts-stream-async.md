---
version: 1.2.0
info:
  title: Pinboard
  version: 1.2.0
servers:
- url: api.pinboard.in/posts/all
  scheme: https
  asyncapi_servers_variables:
    results:
      description: number of results to return. Default is all.
    tag:
      description: filter by up to three tags
    start:
      description: offset value (default is 0)
    fromdt:
      description: return only bookmarks created after this time
    todt:
      description: eturn only bookmarks created before this time
    meta:
      description: include a change detection signature for each bookmark
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/posts_all'
---
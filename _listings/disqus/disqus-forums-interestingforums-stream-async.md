---
version: 1.2.0
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/forums/interestingForums.json
  scheme: https
  asyncapi_servers_variables:
    limit:
      description: Defaults to 5                         Maximum value of 100
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/forums_interestingForums_json'
---
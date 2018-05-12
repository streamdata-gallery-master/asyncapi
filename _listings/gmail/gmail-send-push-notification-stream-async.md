---
version: 1.2.0
x-collection-name: Gmail
info:
  title: Gmail
  version: 1.2.0
servers:
- url: www.googleapis.com/{userId}/watch
  scheme: https
  asyncapi_servers_variables:
    userId:
      description: The user's email address. The special value me can be used to indicate
        the authenticated user.
    body:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/{userId}_watch'
---
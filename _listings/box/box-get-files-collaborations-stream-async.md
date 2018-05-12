---
version: 1.2.0
x-collection-name: Box Get File's Collaborations (stream)
info:
  title: Box
  version: 1.2.0
servers:
- url: api.box.com/files/{FILE_ID}/collaborations
  scheme: https
  asyncapi_servers_variables:
    FILE_ID:
      description: ""
    fields:
      description: Attribute(s) to include in the response
    limit:
      description: The maximum number of items to return in a page
    offset:
      description: The item at which to begin the response
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/files_{FILE_ID}_collaborations'
---
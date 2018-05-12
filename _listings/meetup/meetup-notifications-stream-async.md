---
version: 1.2.0
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/notifications
  scheme: https
  asyncapi_servers_variables:
    fields:
      description: Request that additional fields (separated by commas) be included
        in the output.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/notifications'
---
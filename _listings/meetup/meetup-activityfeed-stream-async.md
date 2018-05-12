---
version: 1.2.0
x-collection-name: Meetup
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/activity
  scheme: https
  asyncapi_servers_variables:
    member_id:
      description: Returns activity from this member's groups. Must be authenticated
        as this member
    page_start:
      description: Starting timestamp for item to return.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/activity'
---
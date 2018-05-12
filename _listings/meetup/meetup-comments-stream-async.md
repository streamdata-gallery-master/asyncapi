---
version: 1.2.0
x-collection-name: Meetup Comments (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/comments
  scheme: https
  asyncapi_servers_variables:
    topic, groupnum:
      description: Return comments for the group with given topic and number
    group_id:
      description: Return comments in groups with these ID numbers [separated by commas]
    group_urlname:
      description: Return comments for the group with this custom URL path
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/comments'
---
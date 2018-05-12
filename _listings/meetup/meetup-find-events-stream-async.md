---
version: 1.2.0
x-collection-name: Meetup Find Events (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/find/events
  scheme: https
  asyncapi_servers_variables:
    lon:
      description: Approximate target longitude
    text:
      description: Raw full text search query
    radius:
      description: Radius in miles. May be 0.0-100.0, 'global' or 'smart', a dynamic
        radius based on the number of active groups in the area. Defaults to member's
        preferred radius
    fields:
      description: A comma-delimited list of optional fields to populate in the response
    lat:
      description: Approximate target latitude
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/find_events'
---
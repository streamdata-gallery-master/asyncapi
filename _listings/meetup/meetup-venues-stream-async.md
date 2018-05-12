---
version: 1.2.0
x-collection-name: Meetup
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/venues
  scheme: https
  asyncapi_servers_variables:
    venue_id:
      description: multiple ids may be separated with commas
    fields:
      description: Request that additional fields (separated by commas) be included
        in the output
    group_id:
      description: multiple ids may be separated with commas
    group_urlname:
      description: path to group from meetup.com, no slashes
    event_id:
      description: multiple ids may be separated with commas
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_venues'
---
---
version: 1.2.0
x-collection-name: Meetup Find Venues (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/find/venues
  scheme: https
  asyncapi_servers_variables:
    zip:
      description: Zipcode of location to limit search to
    text:
      description: Raw full text search query
    country:
      description: A valid two charater country code, desfaults to US
    location:
      description: Raw text location query
    lon:
      description: Approximate longitude
    radius:
      description: Radius in miles. Defaults to 25.0
    fields:
      description: Comma-delimited list of optional fields to append to the response
    lat:
      description: Approximate latitude
    desc:
      description: |-
        Boolean value to indicate to direction ordered results.
        Defaults to false.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/find_venues'
---
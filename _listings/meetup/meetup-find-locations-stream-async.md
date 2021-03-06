---
version: 1.2.0
x-collection-name: Meetup
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/find/locations
  scheme: https
  asyncapi_servers_variables:
    lon:
      description: |-
        Search for locations based on location longitude.
        Must be provided with "lat"
    page:
      description: |-
        The desired number of locations to return in a single set of results.
        Defaults to 200
    offset:
      description: The current offset in the paginated set, represented as an incrementing
        value
    lat:
      description: |-
        Search for locations based on location latitude.
        Must be provided with "lon"
    query:
      description: Search for locations based on city name or zip code
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/find_locations'
---
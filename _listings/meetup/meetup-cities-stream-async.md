---
version: 1.2.0
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/cities
  scheme: https
  asyncapi_servers_variables:
    country:
      description: A valid country code
    query:
      description: Search term and/or zip to look for (if this is specified, max result
        size limited to 10)
    lon:
      description: Longitude to search
    state:
      description: A valid state code for the given country, if the country has states
    radius:
      description: When searching by lat/lon only, specify a radius to search (default
        50 miles)
    lat:
      description: Latitude to search
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_cities'
---
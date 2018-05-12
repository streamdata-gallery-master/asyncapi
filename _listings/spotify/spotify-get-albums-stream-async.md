---
version: 1.2.0
info:
  title: Spotify
  version: 1.2.0
servers:
- url: api.spotify.com/albums
  scheme: https
  asyncapi_servers_variables:
    ids:
      description: A comma-separated list of IDs
    market:
      description: The market (an ISO 3166-1 alpha-2 country code)
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/albums'
---
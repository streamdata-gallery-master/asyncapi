---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/gists
  scheme: https
  asyncapi_servers_variables:
    since:
      description: |
        Timestamp in ISO 8601 format YYYY-MM-DDTHH:MM:SSZ.
        Only gists updated at or after this time are returned.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/gists'
---
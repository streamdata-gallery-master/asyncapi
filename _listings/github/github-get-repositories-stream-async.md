---
version: 1.2.0
x-collection-name: GitHub
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/repositories
  scheme: https
  asyncapi_servers_variables:
    since:
      description: |
        The time should be passed in as UTC in the ISO 8601 format: YYYY-MM-DDTHH:MM:SSZ.
        Example: "2012-10-09T23:39:01Z".
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/repositories'
---
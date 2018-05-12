---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/orgs/{org}/events
  scheme: https
  asyncapi_servers_variables:
    org:
      description: Name of organisation.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/orgs_{org}_events'
---
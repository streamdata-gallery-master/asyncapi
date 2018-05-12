---
version: 1.2.0
x-collection-name: GitHub
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/users/{username}/orgs
  scheme: https
  asyncapi_servers_variables:
    username:
      description: Name of user.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/users_{username}_orgs'
---
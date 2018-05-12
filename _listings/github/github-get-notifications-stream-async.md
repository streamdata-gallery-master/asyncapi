---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/notifications
  scheme: https
  asyncapi_servers_variables:
    all:
      description: True to show notifications marked as read.
    participating:
      description: |
        True to show only notifications in which the user is directly participating
        or mentioned.
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
  - $ref: '#/components/messages/notifications'
---
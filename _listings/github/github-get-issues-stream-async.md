---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/issues
  scheme: https
  asyncapi_servers_variables:
    filter:
      description: |
        Issues assigned to you / created by you / mentioning you / you're
        subscribed to updates for / All issues the authenticated user can see
    state:
      description: ""
    labels:
      description: String list of comma separated Label names. Example - bug,ui,@high.
    sort:
      description: ""
    direction:
      description: ""
    since:
      description: |
        Optional string of a timestamp in ISO 8601 format: YYYY-MM-DDTHH:MM:SSZ.
        Only issues updated at or after this time are returned.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/issues'
---
---
version: 1.2.0
info:
  title: Stack Exchange
  version: 1.2.0
servers:
- url: api.stackexchange.com/answers
  scheme: https
  asyncapi_servers_variables:
    order:
      description: ""
    max:
      description: |
        sort = activity => date
        sort = creation => date
        sort = votes => number
    min:
      description: |
        sort = activity => date
        sort = creation => date
        sort = votes => number
    sort:
      description: ""
    fromdate:
      description: Unix date.
    todate:
      description: Unix date.
    pagesize:
      description: ""
    page:
      description: ""
    filter:
      description: Filter the discussion.
    callback:
      description: |
        All API responses are JSON, we do support JSONP with the callback query parameter.
    site:
      description: Each of these methods operates on a single site at a time, identified
        by the site parameter. This parameter can be the full domain name.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/answers'
---
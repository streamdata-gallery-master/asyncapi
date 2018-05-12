---
version: 1.2.0
info:
  title: Reddit
  version: 1.2.0
servers:
- url: www.reddit.com/api/search_reddit_names.json
  scheme: https
  asyncapi_servers_variables:
    exact:
      description: boolean value
    include_over_18:
      description: boolean value
    include_unadvertisable:
      description: boolean value
    query:
      description: a string up to 50 characters long, consisting of printable characters.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/api_search_reddit_names_json'
---
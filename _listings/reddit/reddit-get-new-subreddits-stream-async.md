---
version: 1.2.0
x-collection-name: Reddit Get New Subreddits (stream)
info:
  title: Reddit
  version: 1.2.0
servers:
- url: www.reddit.com/subreddits/new.json
  scheme: https
  asyncapi_servers_variables:
    query:
      description: a string no longer than 50 characters
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/subreddits_new_json'
---
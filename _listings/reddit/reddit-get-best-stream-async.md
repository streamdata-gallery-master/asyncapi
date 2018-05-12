---
version: 1.2.0
x-collection-name: Reddit
info:
  title: Reddit
  version: 1.2.0
servers:
- url: www.reddit.com/best.json
  scheme: https
  asyncapi_servers_variables:
    after:
      description: fullname of a thing
    before:
      description: fullname of a thing
    count:
      description: 'a positive integer (default: 0)'
    limit:
      description: 'the maximum number of items desired (default: 25, maximum: 100)'
    show:
      description: (optional) the string all
    sr_detail:
      description: (optional) expand subreddits
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/best_json'
---
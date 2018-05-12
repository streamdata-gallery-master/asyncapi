---
version: 1.2.0
x-collection-name: Disqus Categories List (stream)
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/categories/list.json
  scheme: https
  asyncapi_servers_variables:
    forum:
      description: Looks up a forum by ID (aka short name)
    since_id:
      description: Defaults to null
    cursor:
      description: Defaults to null
    limit:
      description: Defaults to 25                         Maximum value of 100
    order:
      description: 'Defaults to asc                         Choices: asc, desc'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/categories_list_json'
---
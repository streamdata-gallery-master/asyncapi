---
version: 1.2.0
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/categories/listThreads.json
  scheme: https
  asyncapi_servers_variables:
    category:
      description: Looks up a category by ID
    since:
      description: Defaults to null                         Unix timestamp (or ISO
        datetime standard)
    related:
      description: 'Defaults to []                         You may specify relations
        to include with your response. Choices: forum, author'
    cursor:
      description: Defaults to null
    limit:
      description: Defaults to 25                         Maximum value of 100
    order:
      description: 'Defaults to desc                         Choices: asc, desc'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/categories_listThreads_json'
---
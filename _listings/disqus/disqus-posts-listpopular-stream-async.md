---
version: 1.2.0
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/posts/listPopular.json
  scheme: https
  asyncapi_servers_variables:
    category:
      description: Defaults to null
    interval:
      description: 'Defaults to 7d                         Choices: 1h, 6h, 12h, 1d,
        3d, 7d, 30d, 60d, 90d'
    forum:
      description: Defaults to null                         Defaults to all forums
        you moderate. Use :all to retrieve all forums.
    thread:
      description: Defaults to null                         Looks up a thread by ID
    query:
      description: Defaults to null
    limit:
      description: Defaults to 25                         Maximum value of 100
    related:
      description: 'Defaults to []                         You may specify relations
        to include with your response. Choices: forum, thread'
    offset:
      description: Defaults to 0
    organization:
      description: Defaults to null                         Looks up an organization
        by ID
    include:
      description: 'Defaults to [  approved]                         Choices: unapproved,
        approved, spam, deleted, flagged, highlighted'
    order:
      description: 'Defaults to popular                         Choices: popular,
        best'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/posts_listPopular_json'
---
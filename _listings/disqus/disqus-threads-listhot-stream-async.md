---
version: 1.2.0
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/threads/listHot.json
  scheme: https
  asyncapi_servers_variables:
    category:
      description: Defaults to null                         Looks up a category by
        ID
    forum:
      description: Defaults to null                         Looks up a forum by ID
        (aka short name)
    author:
      description: Defaults to null                         Looks up a user by ID
        You may look up a user by username using the &#39;username&#39; query type.
    related:
      description: 'Defaults to []                         You may specify relations
        to include with your response. Choices: forum, author, category'
    limit:
      description: Defaults to 25                         Maximum value of 100
    include:
      description: 'Defaults to [  open,  closed]                         Choices:
        open, closed, killed'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/threads_listHot_json'
---
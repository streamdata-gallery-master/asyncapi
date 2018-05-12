---
version: 1.2.0
x-collection-name: Disqus Threads ListPosts (stream)
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/threads/listPosts.json
  scheme: https
  asyncapi_servers_variables:
    thread:
      description: Looks up a thread by ID You may pass us the &#39;ident&#39; or
        &#39;link&#39; query types instead of an ID by including &#39;forum&#39;.
    forum:
      description: Defaults to null                         Looks up a forum by ID
        (aka short name)
    since:
      description: Defaults to null                         Unix timestamp (or ISO
        datetime standard)
    related:
      description: 'Defaults to []                         You may specify relations
        to include with your response. Choices: forum, thread'
    cursor:
      description: Defaults to null
    limit:
      description: Defaults to 25                         Maximum value of 100
    filters:
      description: 'Defaults to []                         Valid values are: 1: Is_Anonymous
        2: Has_Link 3: Has_Low_Rep_Author 4: Has_Bad_Word 5: Is_Flagged 6: No_Issue
        7: Is_Toxic'
    query:
      description: Defaults to null
    include:
      description: 'Defaults to [  approved]                         Choices: unapproved,
        approved, spam, deleted, flagged, highlighted'
    order:
      description: 'Defaults to desc                         Choices: asc, desc'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/threads_listPosts_json'
---
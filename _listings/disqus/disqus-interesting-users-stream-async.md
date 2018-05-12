---
version: 1.2.0
x-collection-name: Disqus
info:
  title: Disqus
  version: 1.2.0
servers:
- url: disqus.com/users/interestingUsers.json
  scheme: https
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/users_interestingUsers_json'
---
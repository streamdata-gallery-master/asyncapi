---
version: 1.2.0
x-collection-name: Instagram Instagram User (stream)
info:
  title: Instagram
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;instagram-user-id&#125;
  scheme: https
  asyncapi_servers_variables:
    idnumeric string:
      description: ID of the Instagram user
    follow_countint32:
      description: Number of Instagram users that this Instagram user follows
    followed_by_countint32:
      description: Number of Instagram users that follow this Instagram user
    has_profile_picturebool:
      description: Indicates whether Instagram Account has a profile picture
    is_privatebool:
      description: Whether the Instagram user is private
    is_publishedbool:
      description: Whether the Instagram user is published
    media_countint32:
      description: Number of active media posted by this Instagram user
    profile_picstring:
      description: URI to user&#039;s Instagram profile picture
    usernamestring:
      description: Instagram username
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;instagram-user-id_#125;'
---
---
version: 1.2.0
x-collection-name: Twitter List Statuses (stream)
info:
  title: Twitter
  version: 1.2.0
servers:
- url: api.twitter.com/lists/statuses.json
  scheme: https
  asyncapi_servers_variables:
    list_id:
      description: The numerical id of the list
    slug:
      description: You can identify a list by its slug instead of its numerical id
    owner_screen_name:
      description: The screen name of the user who owns the list being requested by
        a slug
    owner_id:
      description: The user ID of the user who owns the list being requested by a
        slug
    since_id:
      description: Returns results with an ID greater than the sepcified ID
    max_id:
      description: Returns results with an ID less than or equal to the specified
        ID
    count:
      description: Specifies the number of results to retrieve per page
    include_entities:
      description: Entities are ON by default
    include_rts:
      description: When set to either true, t or 1, the list timeline will contain
        native retweets in addition to the standard stream of tweets
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/lists_statuses_json'
---
---
version: 1.2.0
x-collection-name: Twitter Show Timelines Status (stream)
info:
  title: Twitter
  version: 1.2.0
servers:
- url: api.twitter.com/statuses/user_timeline.json
  scheme: https
  asyncapi_servers_variables:
    count:
      description: Specifies the number of tweets to try and retrieve
    since_id:
      description: Returns result with an ID greater than the specified ID
    max_id:
      description: Returns results with an ID less than or equal to the specified
        ID
    trim_user:
      description: When set to either true, t or 1, each tweet returned in a timeline
        will include a user object
    exclude_replies:
      description: This paramters will prevent from appearing in the returned timeline
    contributor_details:
      description: This paramters enhances the contributors element of the status
        response to include the screen_name of the contributor
    include_rts:
      description: When set to false, the timeline will strip any native retweet
    screen_name:
      description: The user screen name.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/statuses_user_timeline_json'
---
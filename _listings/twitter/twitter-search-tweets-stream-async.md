---
version: 1.2.0
x-collection-name: Twitter Search Tweets (stream)
info:
  title: Twitter
  version: 1.2.0
servers:
- url: api.twitter.com/search/tweets.json
  scheme: https
  asyncapi_servers_variables:
    q:
      description: URL-encoded search query of 500 characters max
    geocode:
      description: returns tweets by users located within given radius
    lang:
      description: restricts tweets to a given language
    locale:
      description: language of query you are sending
    result_type:
      description: specifies type of search results you prefer
    count:
      description: number of tweets to return
    until:
      description: returns tweets created before given date
    since_id:
      description: return results with ID greater than specified
    max_id:
      description: returns results with an ID less than/equal to specified ID
    include_entities:
      description: whether or not to include entities
    callback:
      description: response will use the callback with given name
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search_tweets_json'
---
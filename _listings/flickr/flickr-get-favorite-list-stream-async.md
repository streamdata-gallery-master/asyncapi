---
version: 1.2.0
x-collection-name: Flickr Get Favorite List (stream)
info:
  title: Flickr
  version: 1.2.0
servers:
- url: api.flickr.com/rest?method=flickr.favorites.getList
  asyncapi_servers_variables:
    api_key:
      description: ""
    user_id:
      description: ""
    min_fave_date:
      description: ""
    max_fave_date:
      description: ""
    page:
      description: ""
    per_page:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/rest?method=flickr_favorites_getList'
---
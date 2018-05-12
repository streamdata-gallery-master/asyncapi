---
version: 1.2.0
info:
  title: New York Times
  version: 1.2.0
servers:
- url: api.nytimes.com/topstories/v2/{section}.{format}
  scheme: https
  asyncapi_servers_variables:
    section:
      description: The section the story appears in.
    format:
      description: if this is JSONP or JSON
    callback:
      description: |
        The name of the function the API call results will be passed to. Required when using JSONP. This parameter has only one valid value per section. The format is {section_name}TopStoriesCallback.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/topstories_v2_{section}_{format}'
---
---
version: 1.2.0
x-collection-name: News API Top Headlines (stream)
info:
  title: News API
  version: 1.2.0
servers:
- url: newsapi.orgtop-headlines/
  scheme: https
  asyncapi_servers_variables:
    q:
      description: Keywords or phrases to search for.
    sources:
      description: A comma-seperated string of identifiers (maximum 20) for the news
        sources or blogs you want headlines from. Use the /sources endpoint to locate
        these programmatically or look at the sources index.
    category:
      description: 'Find sources that display news of this category. Possible options:
        business entertainment general health science sports technology . Default:
        all categories.'
    page:
      description: Use this to page through the results.
    pageSize:
      description: The number of results to return per page. 20 is the default, 100
        is the maximum.
    apiKey:
      description: Your API key. Alternatively you can provide this via the X-Api-Key
        HTTP header.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/top-headlines_'
---
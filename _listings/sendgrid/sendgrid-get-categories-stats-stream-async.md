---
version: 1.2.0
x-collection-name: SendGrid Get Categories Stats (stream)
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/categories/stats
  scheme: https
  asyncapi_servers_variables:
    start_date:
      description: The starting date of the statistics to retrieve. Must follow format
        YYYY-MM-DD
    end_date:
      description: The end date of the statistics to retrieve. Defaults to today.
        Must follow format YYYY-MM-DD.
    categories:
      description: The individual categories that you want to retrieve statistics
        for. You may include up to 10 different categories.
    limit:
      description: The number of results to include.
    offset:
      description: The number of results to skip.
    aggregated_by:
      description: How to group the statistics. Must be either "day", "week", or "month".
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/categories_stats'
---
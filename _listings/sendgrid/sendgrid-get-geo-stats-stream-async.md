---
version: 1.2.0
x-collection-name: SendGrid Get Geo Stats (stream)
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/geo/stats
  scheme: https
  asyncapi_servers_variables:
    limit:
      description: How many results to include on each page.
    offset:
      description: How many results to exclude.
    aggregated_by:
      description: How you would like the statistics to be grouped. Must be either
        "day", "week", or "month".
    start_date:
      description: The starting date of the statistics to retrieve. Must be in format
        YYYY-MM-DD
    end_date:
      description: 'The end date of the statistics to retrieve. '
    country:
      description: The country you would like to see statistics for. Currently only
        supported for US and CA.
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/geo_stats'
---
---
version: 1.2.0
x-collection-name: SendGrid Get Stats (stream)
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/stats
  scheme: https
  asyncapi_servers_variables:
    limit:
      description: The number of results to return.
    offset:
      description: The point in the list to begin retrieving results.
    aggregated_by:
      description: How to group the statistics. Must be either "day", "week", or "month".
    start_date:
      description: The starting date of the statistics to retrieve. Must follow format
        YYYY-MM-DD.
    end_date:
      description: The end date of the statistics to retrieve. Defaults to today.
        Must follow format YYYY-MM-DD.
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/stats'
---
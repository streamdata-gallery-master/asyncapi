---
version: 1.2.0
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/devices/stats
  scheme: https
  asyncapi_servers_variables:
    end_date:
      description: The end date of the statistics to retrieve. Defaults to today.
    limit:
      description: How many results to include on each page.
    offset:
      description: How many results to exclude.
    aggregated_by:
      description: How to group the statistics. Must be either "day", "week", or "month".
    start_date:
      description: The starting date of the statistics to retrieve.
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/devices_stats'
---
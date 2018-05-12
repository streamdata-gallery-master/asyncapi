---
version: 1.2.0
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/suppression/blocks
  scheme: https
  asyncapi_servers_variables:
    start_time:
      description: Refers start of the time range in unix timestamp when a blocked
        email was created (inclusive).
    end_time:
      description: Refers end of the time range in unix timestamp when a blocked email
        was created (inclusive).
    limit:
      description: Limit the number of results to be displayed per page.
    offset:
      description: The point in the list to begin displaying results.
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/suppression_blocks'
---
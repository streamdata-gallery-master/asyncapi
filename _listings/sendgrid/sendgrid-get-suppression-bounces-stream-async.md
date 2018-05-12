---
version: 1.2.0
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/suppression/bounces
  scheme: https
  asyncapi_servers_variables:
    start_time:
      description: Refers start of the time range in unix timestamp when a bounce
        was created (inclusive).
    end_time:
      description: Refers end of the time range in unix timestamp when a bounce was
        created (inclusive).
    Accept:
      description: ""
    No Name:
      description: ""
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/suppression_bounces'
---
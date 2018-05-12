---
version: 1.2.0
info:
  title: SendGrid
  version: 1.2.0
servers:
- url: api.sendgrid.com/campaigns
  scheme: https
  asyncapi_servers_variables:
    limit:
      description: The number of results you would like to receive at a time.
    offset:
      description: The index of the first campaign to return, where 0 is the first
        campaign.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/campaigns'
---
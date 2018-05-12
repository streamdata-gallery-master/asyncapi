---
version: 1.2.0
info:
  title: Stripe
  version: 1.2.0
servers:
- url: api.stripe.com/balance
  scheme: https
  asyncapi_servers_variables:
    expand:
      description: Specifies which fields in the response should be expanded.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/balance'
---
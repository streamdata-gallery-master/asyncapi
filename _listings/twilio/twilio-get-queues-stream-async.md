---
version: 1.2.0
x-collection-name: Twilio Get Queues (stream)
info:
  title: Twilio
  version: 1.2.0
servers:
- url: api.twilio.com/Accounts/{AccountSid}/Queues
  scheme: https
  asyncapi_servers_variables:
    AccountSid:
      description: The ID for the Twilio account.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/Accounts_{AccountSid}_Queues'
---
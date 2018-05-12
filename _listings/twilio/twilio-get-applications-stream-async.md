---
version: 1.2.0
info:
  title: Twilio
  version: 1.2.0
servers:
- url: api.twilio.com/Accounts/{AccountSid}/Applications.{format}
  scheme: https
  asyncapi_servers_variables:
    AccountSid:
      description: The ID for the Twilio account.
    format:
      description: By default, Twilios REST API returns XML. You may obtain CSV, JSON
        or HTML by appending .csv, .json, or .html.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/Accounts_{AccountSid}_Applications_{format}'
---
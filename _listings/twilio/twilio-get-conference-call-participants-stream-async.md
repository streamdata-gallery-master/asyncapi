---
version: 1.2.0
x-collection-name: Twilio Get Conference Call Participants (stream)
info:
  title: Twilio
  version: 1.2.0
servers:
- url: api.twilio.com/Accounts/{AccountSid}/Conferences/{ConferenceSid}/Participants.{format}
  scheme: https
  asyncapi_servers_variables:
    AccountSid:
      description: The ID for the Twilio account.
    ConferenceSid:
      description: A 34 character string that uniquely identifies the conference call
        object.
    format:
      description: By default, Twilios REST API returns XML. You may obtain CSV, JSON
        or HTML by appending .csv, .json, or .html.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/Accounts_{AccountSid}_Conferences_{ConferenceSid}_Participants_{format}'
---
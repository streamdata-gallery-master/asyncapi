---
version: 1.2.0
info:
  title: Eventbrite
  version: 1.2.0
servers:
- url: www.eventbriteapi.com/events/{id}/attendees/
  scheme: https
  asyncapi_servers_variables:
    status:
      description: 'Limits results to either confirmed attendees or cancelled/refunded/etc.
        attendees (Valid choices are: attending, not_attending, or unpaid)'
    changed_since:
      description: Only return attendees changed on or after the time given
    last_item_seen:
      description: Only return attendees changed on or after the time given and with
        an id bigger than last item seen
    attendee_ids:
      description: Only return attendees whose ids are in this list
    id:
      description: The unique event id.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/events_{id}_attendees_'
---
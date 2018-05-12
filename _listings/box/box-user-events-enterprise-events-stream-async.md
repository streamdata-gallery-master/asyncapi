---
version: 1.2.0
info:
  title: Box
  version: 1.2.0
servers:
- url: api.box.com/events
  scheme: https
  asyncapi_servers_variables:
    stream_position:
      description: "The location in the event stream at which you want to start receiving
        events. Can specify special case \u2018now\u2019 to get 0 events and the latest
        stream position for initialization."
    stream_type:
      description: 'Limits the type of events returned: all: returns everything, changes:
        returns tree changes, sync: returns tree changes only for sync folders'
    limit:
      description: Limits the number of events returned
    event_type:
      description: A comma-separated list of events to filter by
    created_after:
      description: A lower bound on the timestamp of the events returned
    created_before:
      description: An upper bound on the timestamp of the events returned
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/events'
---
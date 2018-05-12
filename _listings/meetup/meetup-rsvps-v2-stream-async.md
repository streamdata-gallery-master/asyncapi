---
version: 1.2.0
x-collection-name: Meetup RSVPs v2 (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/rsvps
  scheme: https
  asyncapi_servers_variables:
    fields:
      description: Parameter for requesting optional response properties, set to other_services
        for a list of third party services
    rsvp:
      description: Filters response on RSVP status. "yes" if member RSVP'd yes otherwise
        "no"
    event_id:
      description: Multiple alphanumeric ids may be separated with commas
    callback:
      description: "Name of a function to be called with an array of RSVP notification
        objects. If this \nparameter is not supplied, the chunked stream is joined
        instead."
    since_mtime:
      description: Should be supplied for all but the first polling request, so that
        any missed notifications are can be sent in an immediate response
    since_count:
      description: Request that some number of recent messages be sent immediately,
        if available. May not be specified in the same request as since_mtime.
    api_version:
      description: "2"
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_rsvps'
---
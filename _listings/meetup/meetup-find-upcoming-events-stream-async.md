---
version: 1.2.0
x-collection-name: Meetup Find Upcoming Events (stream)
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/find/upcoming_events
  scheme: https
  asyncapi_servers_variables:
    end_time_range:
      description: "Return events that start before this time. The time must follow
        this format: HH:MM:SS. The time is exlusive. A start_time_range must also
        be present\n           "
    lon:
      description: Approximate target longitude
    end_date_range:
      description: "Return events that start before this date. The date must follow
        this format: YYYY-MM-DDTHH:MM:SS.\n           "
    topic_category:
      description: Numeric topic category identifier for filtering recommendations
        by a topic category
    excluded_groups:
      description: "IDs for groups to exclude from the returned events. excluded_groups
        overrides the include and only\nvalues for self_groups. In other words, if
        excluded_groups is nonempty,\nthen groups specified in excluded_groups will
        be excluded\neven if they are in the set of groups the authenticated member
        belongs to.\n           "
    start_date_range:
      description: "Return events that start after this date. The date must follow
        this format: YYYY-MM-DDTHH:MM:SS.\nIt defaults to the current date and time.\n
        \          "
    start_time_range:
      description: "Return events that start after this time. The time must follow
        this format: HH:MM:SS. The time is inclusive. An end_time_range must also
        be present.\n           "
    page:
      description: A target minimum number of events to return in a single page of
        results. The number returned is non-deterministic but a best-effort attempt
        will be made to return at least some. Defaults to 32
    text:
      description: Full text search query
    radius:
      description: Radius in miles. May be 0.0-100.0, 'global' or 'smart', a dynamic
        radius based on the number of active groups in the area. Defaults to member's
        preferred radius
    fields:
      description: A comma-delimited list of optional fields to populate in the response
    self_groups:
      description: "set to 'include' or 'exclude' or 'only' get groups that the member
        belongs to. Defaults to 'include.'\nWhen self_groups is set to only and the
        order is set to time, the following fields are disregarded: page, end_date_range,
        lat and lon.\n           "
    lat:
      description: Approximate target latitude
    order:
      description: "The sort order of returned events.\nValid values include: 'best'
        and 'time'.\n'best' orders events by recommendation score, while 'time' orders
        events by the by the event's start time in increasing order.\nDefaults to
        'best'.\n           "
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/find_upcoming_events'
---
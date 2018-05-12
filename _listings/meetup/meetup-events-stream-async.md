---
version: 1.2.0
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/events
  scheme: https
  asyncapi_servers_variables:
    rsvp:
      description: Filters events by the currently authenticated member's RSVP status.
        May be a comma delimited list of "yes", "no", "waitlist", "maybe" or "none"
    group_urlname:
      description: Path to group from meetup.com, no slashes
    event_id:
      description: Multiple ids may be separated with commas
    group_id:
      description: Multiple ids may be separated with commas
    limited_events:
      description: 'Include limited event information for private groups that wish
        to expose only a small amount of information about their events. This includes
        just: id, name, utc_offset, time, duration, yes_rsvp_count, waitlist_count,
        group, visibility, timezone. Value must be true or false.'
    text_format:
      description: Format of the description text, "html" or "plain". Defaults to
        "html"
    group_domain:
      description: Group custom domain
    venue_id:
      description: Multiple ids may be separated with commas
    member_id:
      description: Single member id, to find events in this member's groups
    time:
      description: 'Return events scheduled within the given time range, defined by
        two times separated with a single comma. Each end of the range may be specified
        with relative dates, such as "1m" for one month from now, or by absolute time
        in milliseconds since the epoch. If an endpoint is omitted, the range is unbounded
        on that end. The default value is unbounded on both ends (though restricted
        to the search window described above). Note: to retrieve past events you must
        also update status value'
    fields:
      description: Request that additional fields (separated by commas) be included
        in the output
    status:
      description: Status may be "upcoming", "past", "proposed", "suggested", "cancelled",
        "draft" or multiple separated by a comma. The default is "upcoming", which
        includes Meetups that are happening now according to their **duration**. Meetups
        that are "proposed" or "suggested" do not have a date assigned; the former
        are listed on the site as <i>official</i> while the latter appear as <i>in
        the making</i>. Drafts are only visible to organizers of groups hosting the
        events.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_events'
---
---
version: 1.2.0
x-collection-name: Meetup
info:
  title: Meetup
  version: 1.2.0
servers:
- url: api.meetup.com/2/members
  scheme: https
  asyncapi_servers_variables:
    topic,groupnum:
      description: Return members for the group with given topic and number
    group_urlname:
      description: Return members for the group with the given custom URL path
    member_id:
      description: Return the member with this ID
    fields:
      description: Request that additional fields (separated by commas) be included
        in the output.
    group_id:
      description: Return members in groups with these ID numbers, separated by commas
    service:
      description: Match users by the external services they've linked to their member
        account, specified as "servicename:identifier". For example, "service=twitter:@MeetupAPI"
        finds any member account that lists @MeetupAPI as its Twitter name (none,
        currently). You can query against several at a time by separating them with
        commas. Facebook identifiers should be provided as numeric values
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/2_members'
---
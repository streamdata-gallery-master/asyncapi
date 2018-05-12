---
version: 1.2.0
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;conversation-id&#125;
  scheme: https
  asyncapi_servers_variables:
    id:
      description: The ID of a conversation, in a format similar to t_id.000000000000000
    link:
      description: The url to the thread
    snippet:
      description: The snippet of the most recent message in a conversation
    updated_time:
      description: Last update time
    message_count:
      description: An estimate of the number of messages
    unread_count:
      description: An estimate of the number of unread messages
    Vector:
      description: Vector
    participants:
      description: People and Pages who are on this conversation
    senders:
      description: People who have sent a message
    can_reply:
      description: Whether the Page is able to reply
    is_subscribed:
      description: Whether the Page is subscribed to the conversation
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;conversation-id_#125;'
---
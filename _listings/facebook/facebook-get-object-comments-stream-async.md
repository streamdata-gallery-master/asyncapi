---
version: 1.2.0
x-collection-name: Facebook Get Object Comments (stream)
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;object-id&#125;/comments
  scheme: https
  asyncapi_servers_variables:
    order:
      description: "Order in which comments were returned.\n\nchronological: Comments
        sorted by the oldest comments first. \nreverse_chronological: Comments sorted
        by the newest comments first."
    total_count:
      description: |-
        The count of comments on this node. It is important to note that this value is changed depending on the filter modifier being used (where comment replies are available):

        if filter is stream then total_count will be a count of all comments (including replies) on the node.
        if filter is toplevel then total_count will be a count of all top-level comments on the node.
        Note: total_count can be greater than or equal to the actual number of comments returned due to comment privacy or deletion.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;object-id_#125;_comments'
---
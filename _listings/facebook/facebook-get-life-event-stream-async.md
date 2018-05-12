---
version: 1.2.0
x-collection-name: Facebook
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;life-event-id&#125;
  scheme: https
  asyncapi_servers_variables:
    created_timedatetime:
      description: The time when this milestone was publishedDefault
    descriptionstring:
      description: Description of the milestoneDefault
    end_timedatetime:
      description: The time when this milestone came to an endDefault
    fromPage:
      description: The information of the Page that ownes the milestoneDefault
    idnumeric string:
      description: The milestone IDDefault
    is_hiddenbool:
      description: Whether the milestone is hidden or notDefault
    start_timedatetime:
      description: The time when this milestone was startedDefault
    titlestring:
      description: The title of the milestoneDefault
    updated_timedatetime:
      description: The time when this milestone was updatedDefault
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;life-event-id_#125;'
---
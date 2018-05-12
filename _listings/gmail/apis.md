---
name: Gmail
description: The Gmail API is a RESTful API that can be used to access Gmail mailboxes
  and send mail. For most web applications (including mobile apps), the Gmail API
  is the best choice for authorized access to a users Gmail data.
image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/gmail-icon.png
x-kinRank: "10"
x-alexaRank: ""
tags:
- Stack Network
- Stack
- Productivity
- Google APIs
- Email
created: "2018-05-12"
modified: "2018-05-12"
url: https://raw.githubusercontent.com/streamdata-gallery-topics/asyncapi/master/_listings/gmail/apis.yaml
specificationVersion: "0.14"
apis:
- name: Gmail Get History (stream)
  description: The Gmail API is a RESTful API that can be used to access Gmail mailboxes
    and send mail
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/gmail-icon.png
  humanURL: https://www.google.com/gmail/
  properties:
  - type: x-asyncapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/asyncapi/master/_listings/gmail/gmail-get-history-stream-async.md
  tags:
  - Stack Network
  - Stack
  - Productivity
  - Google APIs
  - Email
- name: Gmail Get Message (stream)
  description: The Gmail API is a RESTful API that can be used to access Gmail mailboxes
    and send mail
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/gmail-icon.png
  humanURL: https://www.google.com/gmail/
  properties:
  - type: x-asyncapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/asyncapi/master/_listings/gmail/gmail-get-message-stream-async.md
  tags:
  - Stack Network
  - Stack
  - Productivity
  - Google APIs
  - Email
- name: Gmail Get Threads (stream)
  description: The Gmail API is a RESTful API that can be used to access Gmail mailboxes
    and send mail
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/gmail-icon.png
  humanURL: https://www.google.com/gmail/
  properties:
  - type: x-asyncapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/asyncapi/master/_listings/gmail/gmail-get-threads-stream-async.md
  tags:
  - Stack Network
  - Stack
  - Productivity
  - Google APIs
  - Email
- name: Gmail Send Push Notification (stream)
  description: The Gmail API is a RESTful API that can be used to access Gmail mailboxes
    and send mail
  image: http://kinlane-productions.s3.amazonaws.com/api-evangelist-site/company/logos/gmail-icon.png
  humanURL: https://www.google.com/gmail/
  properties:
  - type: x-asyncapi-spec
    url: https://raw.githubusercontent.com/streamdata-gallery-topics/asyncapi/master/_listings/gmail/gmail-send-push-notification-stream-async.md
  tags:
  - Stack Network
  - Stack
  - Productivity
  - Google APIs
  - Email
x-common:
- type: x-auth-scopes
  url: https://developers.google.com/gmail/api/auth/scopes
- type: x-authentication
  url: https://developers.google.com/gmail/api/auth/about-auth
- type: x-developer
  url: https://developers.google.com/gmail/api/
- type: x-documentation
  url: https://developers.google.com/gmail/api/v1/reference/
- type: x-twitter
  url: https://twitter.com/gmail
- type: x-website
  url: https://www.google.com/gmail/
include: []
maintainers:
- FN: Kin Lane
  x-twitter: apievangelist
  email: info@apievangelist.com
---
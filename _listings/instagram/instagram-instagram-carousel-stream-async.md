---
version: 1.2.0
info:
  title: Instagram
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;instagram-carousel-id&#125;
  scheme: https
  asyncapi_servers_variables:
    idnumeric string:
      description: ID of the Instagram carousel
    caption_textstring:
      description: Caption text
    comment_countint32:
      description: Number of comments
    content_typeint32:
      description: 0 for photo, 1 for video
    display_urlstring:
      description: URL of the photo or cover frame
    like_countint32:
      description: Number of likes
    owner_instagram_userInstagramUser:
      description: The Instagram user that owns this carousel
    permalinkstring:
      description: Instagram permalink of the first asset
    taken_atdatetime:
      description: When the media was created
    video_urlstring:
      description: URL of the video
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;instagram-carousel-id_#125;'
---
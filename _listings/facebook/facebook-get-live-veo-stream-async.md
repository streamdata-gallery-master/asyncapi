---
version: 1.2.0
info:
  title: Facebook
  version: 1.2.0
servers:
- url: graph.facebook.com/&#123;live-video-id&#125;
  scheme: https
  asyncapi_servers_variables:
    idnumeric string:
      description: The live video ID
    ad_break_configLiveVideoAdBreakConfig:
      description: The ad break configurations for clients implementing triggering
        an ad break ui. Contains ad break eligibility and constants to renderthe ui.
    ad_break_failure_reasonenum:
      description: Ad Break failure reason
    broadcast_start_timedatetime:
      description: The time the video was initially published
    copyrightVideoCopyright:
      description: The copyright information for the live video
    creation_timedatetime:
      description: The creation time of the live video
    dash_preview_urlstring:
      description: Preview URL for dash player
    descriptionstring:
      description: The description of the live video
    embed_htmlstring:
      description: The embed html of the live videoDefault
    is_manual_modebool:
      description: Whether schedule live is in manual mode, in which live video will
        start manually instead of on schedled time
    is_reference_onlybool:
      description: Whether the live video is exclusively used for copyright monitoring
    live_viewsunsigned int32:
      description: The instant viewer count of the live video now
    permalink_urlstring:
      description: The permalink URL of this video on Facebook.
    planned_start_timedatetime:
      description: Planned start time for a live video
    seconds_leftint32:
      description: Seconds left in the maximum possible duration for this live video
    secure_stream_urlstring:
      description: The secure stream url of the live video. Check with your encoder
        whether this is supported before adaptingDefault
    statusenum:
      description: The status of the live videoDefault
    stream_urlstring:
      description: The stream url of the live videoDefault
    titlestring:
      description: The title of the live videoDefault
    videoVideo:
      description: The inside video of live video - only visible when the live video
        has ended.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/_#123;live-video-id_#125;'
---
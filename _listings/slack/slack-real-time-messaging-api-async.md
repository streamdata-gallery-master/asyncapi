---
version: 1.2.0
x-collection-name: Slack
info:
  title: Slack Real Time Messaging API
  version: 1.2.0
servers:
- url: https://slack.com/api/rtm.connect
  scheme: https
  schemeVersion: "1.1"
events:
  send:
  - $ref: '#/components/messages/outgoingMessage'
  - $ref: '#/components/messages/hello'
  - $ref: '#/components/messages/connectionError'
  - $ref: '#/components/messages/accountsChanged'
  - $ref: '#/components/messages/botAdded'
  - $ref: '#/components/messages/botChanged'
  - $ref: '#/components/messages/channelArchive'
  - $ref: '#/components/messages/channelCreated'
  - $ref: '#/components/messages/channelDeleted'
  - $ref: '#/components/messages/channelHistoryChanged'
  - $ref: '#/components/messages/channelJoined'
  - $ref: '#/components/messages/channelLeft'
  - $ref: '#/components/messages/channelMarked'
  - $ref: '#/components/messages/channelRename'
  - $ref: '#/components/messages/channelUnarchive'
  - $ref: '#/components/messages/commandsChanged'
  - $ref: '#/components/messages/dndUpdated'
  - $ref: '#/components/messages/dndUpdatedUser'
  - $ref: '#/components/messages/emailDomainChanged'
  - $ref: '#/components/messages/emojiRemoved'
  - $ref: '#/components/messages/emojiAdded'
  - $ref: '#/components/messages/fileChange'
  - $ref: '#/components/messages/fileCommentAdded'
  - $ref: '#/components/messages/fileCommentDeleted'
  - $ref: '#/components/messages/fileCommentEdited'
  - $ref: '#/components/messages/fileCreated'
  - $ref: '#/components/messages/fileDeleted'
  - $ref: '#/components/messages/filePublic'
  - $ref: '#/components/messages/fileShared'
  - $ref: '#/components/messages/fileUnshared'
  - $ref: '#/components/messages/goodbye'
  - $ref: '#/components/messages/groupArchive'
  - $ref: '#/components/messages/groupClose'
  - $ref: '#/components/messages/groupHistoryChanged'
  - $ref: '#/components/messages/groupJoined'
  - $ref: '#/components/messages/groupLeft'
  - $ref: '#/components/messages/groupMarked'
  - $ref: '#/components/messages/groupOpen'
  - $ref: '#/components/messages/groupRename'
  - $ref: '#/components/messages/groupUnarchive'
  - $ref: '#/components/messages/imClose'
  - $ref: '#/components/messages/imCreated'
  - $ref: '#/components/messages/imMarked'
  - $ref: '#/components/messages/imOpen'
  - $ref: '#/components/messages/manualPresenceChange'
  - $ref: '#/components/messages/memberJoinedChannel'
  - $ref: '#/components/messages/message'
  receive: []
components:
  messages:
    hello:
      summary: First event received upon connection.
      payload:
        properties:
          type:
            type: string
            description: ""
    connectionError:
      summary: Event received when a connection error happens.
      payload:
        properties:
          type:
            type: string
            description: ""
    error:
      payload:
        properties:
          code:
            type: number
            description: ""
          msg:
            type: string
            description: ""
    accountsChanged:
      summary: The list of accounts a user is signed into has changed.
      payload:
        properties:
          type:
            type: string
            description: ""
    botAdded:
      summary: A bot user was added.
      payload:
        properties:
          type:
            type: string
            description: ""
    bot:
      payload:
        properties:
          id:
            type: string
            description: ""
          app_id:
            type: string
            description: ""
          name:
            type: string
            description: ""
    botChanged:
      summary: A bot user was changed.
      payload:
        properties:
          type:
            type: string
            description: ""
    channelArchive:
      summary: A channel was archived.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          user:
            type: string
            description: ""
    channelCreated:
      summary: A channel was created.
      payload:
        properties:
          type:
            type: string
            description: ""
    channel:
      payload:
        properties:
          id:
            type: string
            description: ""
          name:
            type: string
            description: ""
          created:
            type: number
            description: ""
          creator:
            type: string
            description: ""
          user:
            type: string
            description: ""
    channelDeleted:
      summary: A channel was deleted.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    channelHistoryChanged:
      summary: Bulk updates were made to a channel's history.
      payload:
        properties:
          type:
            type: string
            description: ""
          latest:
            type: string
            description: ""
          ts:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    channelJoined:
      summary: You joined a channel.
      payload:
        properties:
          type:
            type: string
            description: ""
    channelLeft:
      summary: You left a channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    channelMarked:
      summary: Your channel read marker was updated.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          ts:
            type: string
            description: ""
    channelRename:
      summary: A channel was renamed.
      payload:
        properties:
          type:
            type: string
            description: ""
    channelUnarchive:
      summary: A channel was unarchived.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          user:
            type: string
            description: ""
    commandsChanged:
      summary: A slash command has been added or changed.
      payload:
        properties:
          type:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    dndUpdated:
      summary: Do not Disturb settings changed for the current user.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
    dnd_status:
      payload:
        properties:
          dnd_enabled:
            type: boolean
            description: ""
          next_dnd_start_ts:
            type: number
            description: ""
          next_dnd_end_ts:
            type: number
            description: ""
          snooze_enabled:
            type: boolean
            description: ""
          snooze_endtime:
            type: number
            description: ""
    dndUpdatedUser:
      summary: Do not Disturb settings changed for a member.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
    emailDomainChanged:
      summary: The workspace email domain has changed.
      payload:
        properties:
          type:
            type: string
            description: ""
          email_domain:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    emojiRemoved:
      summary: A custom emoji has been removed.
      payload:
        properties:
          type:
            type: string
            description: ""
          subtype:
            type: string
            description: ""
    names:
      payload:
        properties:
          event_ts:
            type: string
            description: ""
    emojiAdded:
      summary: A custom emoji has been added.
      payload:
        properties:
          type:
            type: string
            description: ""
          subtype:
            type: string
            description: ""
          name:
            type: string
            description: ""
          value:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    fileChange:
      summary: A file was changed.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    file:
      payload:
        properties:
          id:
            type: string
            description: ""
    fileCommentAdded:
      summary: A file comment was added.
      payload:
        properties:
          type:
            type: string
            description: ""
          comment:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileCommentDeleted:
      summary: A file comment was deleted.
      payload:
        properties:
          type:
            type: string
            description: ""
          comment:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileCommentEdited:
      summary: A file comment was edited.
      payload:
        properties:
          type:
            type: string
            description: ""
          comment:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileCreated:
      summary: A file was created.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileDeleted:
      summary: A file was deleted.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    filePublic:
      summary: A file was made public.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileShared:
      summary: A file was shared.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    fileUnshared:
      summary: A file was unshared.
      payload:
        properties:
          type:
            type: string
            description: ""
          file_id:
            type: string
            description: ""
    goodbye:
      summary: The server intends to close the connection soon.
      payload:
        properties:
          type:
            type: string
            description: ""
    groupArchive:
      summary: A private channel was archived.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    groupClose:
      summary: You closed a private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    groupHistoryChanged:
      summary: Bulk updates were made to a private channel's history.
      payload:
        properties:
          type:
            type: string
            description: ""
          latest:
            type: string
            description: ""
          ts:
            type: string
            description: ""
          event_ts:
            type: string
            description: ""
    groupJoined:
      summary: You joined a private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
    groupLeft:
      summary: You left a private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    groupMarked:
      summary: A private channel read marker was updated.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          ts:
            type: string
            description: ""
    groupOpen:
      summary: You opened a private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
          channel:
            type: string
            description: ""
    groupRename:
      summary: A private channel was renamed.
      payload:
        properties:
          type:
            type: string
            description: ""
    groupUnarchive:
      summary: A private channel was unarchived.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          user:
            type: string
            description: ""
    imClose:
      summary: You closed a DM.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          user:
            type: string
            description: ""
    imCreated:
      summary: A DM was created.
      payload:
        properties:
          type:
            type: string
            description: ""
    imMarked:
      summary: A direct message read marker was updated.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          ts:
            type: string
            description: ""
    imOpen:
      summary: You opened a DM.
      payload:
        properties:
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          user:
            type: string
            description: ""
    manualPresenceChange:
      summary: You manually updated your presence.
      payload:
        properties:
          type:
            type: string
            description: ""
          presence:
            type: string
            description: ""
    memberJoinedChannel:
      summary: A user joined a public or private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          channel_type:
            type: string
            description: ""
          team:
            type: string
            description: ""
          inviter:
            type: string
            description: ""
    memberLeftChannel:
      summary: A user left a public or private channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          channel_type:
            type: string
            description: ""
          team:
            type: string
            description: ""
    message:
      summary: A message was sent to a channel.
      payload:
        properties:
          type:
            type: string
            description: ""
          user:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          text:
            type: string
            description: ""
          ts:
            type: string
            description: ""
    edited:
      payload:
        properties:
          user:
            type: string
            description: ""
          ts:
            type: string
            description: ""
    outgoingMessage:
      summary: A message was sent to a channel.
      payload:
        properties:
          id:
            type: number
            description: ""
          type:
            type: string
            description: ""
          channel:
            type: string
            description: ""
          text:
            type: string
            description: ""
---
---
version: 1.2.0
info:
  title: Gmail
  version: 1.2.0
servers:
- url: www.googleapis.com/{userId}/history
  scheme: https
  asyncapi_servers_variables:
    userId:
      description: The user's email address. The special value me can be used to indicate
        the authenticated user.
    historyTypes:
      description: History types to be returned by the function
    labelId:
      description: Only return messages with a label matching the ID.
    maxResults:
      description: The maximum number of history records to return.
    pageToken:
      description: Page token to retrieve a specific page of results in the list.
    startHistoryId:
      description: Required. Returns history records after the specified startHistoryId.
        The supplied startHistoryId should be obtained from the historyId of a message,
        thread, or previous list response. History IDs increase chronologically but
        are not contiguous with random gaps in between valid IDs. Supplying an invalid
        or out of date startHistoryId typically returns an HTTP 404 error code. A
        historyId is typically valid for at least a week, but in some rare circumstances
        may be valid for only a few hours. If you receive an HTTP 404 error response,
        your application should perform a full sync. If you receive no nextPageToken
        in the response, there are no updates to retrieve and you can store the returned
        historyId for a future request.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/{userId}_history'
---
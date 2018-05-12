---
version: 1.2.0
x-collection-name: Google Sheets Get Spreadsheet (stream)
info:
  title: Google Sheets
  version: 1.2.0
servers:
- url: sheets.googleapis.com/spreadsheets/{spreadsheetId}
  scheme: https
  asyncapi_servers_variables:
    spreadsheetId:
      description: The spreadsheet to request.
    ranges:
      description: The ranges to retrieve from the spreadsheet.
    includeGridData:
      description: |-
        True if grid data should be returned.
        This parameter is ignored if a field mask was set in the request.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/spreadsheets_{spreadsheetId}'
---
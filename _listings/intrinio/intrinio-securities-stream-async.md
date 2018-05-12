---
version: 1.2.0
info:
  title: Intrinio API
  version: 1.2.0
servers:
- url: api.intrinio.com/securities
  scheme: https
  asyncapi_servers_variables:
    identifier:
      description: ' the identifier for the legal entity or a security associated
        with the company: '
    query:
      description: ' a string query search of security name or ticker symbol with
        the returned results being the relevant securities in compacted list format.'
    exch_symbol:
      description: ' the Intrinio Stock Market Symbol, to specify the exchange for
        the list of securities: '
    last_crsp_adj_date:
      description: ' a date value that returns the list of securities that have had
        adjusted stock prices due to a corporate event after this date: YYYY'
    page_size:
      description: ' an integer greater than 1 for specifying the number of results
        on each page.'
    page_number:
      description: ' an integer greater than or equal to 1 for specifying the page
        number for the return values.'
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/securities'
---
---
version: 1.2.0
x-collection-name: New York Times Article Search (stream)
info:
  title: New York Times
  version: 1.2.0
servers:
- url: api.nytimes.com/search/v2/articlesearch.json
  scheme: https
  asyncapi_servers_variables:
    q:
      description: |
        Search query term. Search is performed on the article body, headline and byline.
    fq:
      description: "\"Filtered search query using standard Lucene syntax. \n\nThe
        filter query can be specified with or without a limiting field: label. \n\nSee
        Filtering Your Search for more information about filtering.\"\n"
    begin_date:
      description: "\"Format: YYYYMMDD \n\nRestricts responses to results with publication
        dates of the date specified or later.\"\n"
    end_date:
      description: "\"Format: YYYYMMDD \n\nRestricts responses to results with publication
        dates of the date specified or earlier.\"\n"
    sort:
      description: |
        "By default, search results are sorted by their relevance to the query term (q). Use the sort parameter to sort by pub_date."
    fl:
      description: "\"Comma-delimited list of fields (no limit)\n\n  Limits the fields
        returned in your search results. By default (unless you include an fl list
        in your request), the following fields are returned: \n  \n  web_url\n  \n
        \ snippet\n  \n  lead_paragraph\n  \n  abstract\n  \n  print_page\n  \n  blog\n
        \ \n  source\n  \n  multimedia\n  \n  headline\n  \n  keywords\n  \n  pub_date\n
        \ \n  document_type\n  \n  news_desk\n  \n  byline\n  \n  type_of_material\n
        \ \n  _id\n  \n  word_count\"\n"
    hl:
      description: |
        Enables highlighting in search results. When set to true, the query term (q) is highlighted in the headline and lead_paragraph fields.

        Note: If highlighting is enabled, snippet will be returned even if it is not specified in your fl list."
    page:
      description: |
        "The value of page corresponds to a set of 10 results (it does not indicate the starting number of the result set). For example, page=0 corresponds to records 0-9. To return records 10-19, set page to 1, not 10."
    facet_field:
      description: |
        Comma-delimited list of facets

        Specifies the sets of facet values to include in the facets array at the end of response, which collects the facet values from all the search results. By default no facet fields will be returned. Below is the list of valid facets:

        section_name

        document_type

        type_of_material

        source

        day_of_week

        To learn more about using facets, see Using Facets.
    facet_filter:
      description: |
        When set to true, facet counts will respect any applied filters (fq, date range, etc.) in addition to the main query term. To filter facet counts, specifying at least one facet_field is required. To learn more about using facets, see Using Facets.
    api-key:
      description: The API key.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search_v2_articlesearch_json'
---
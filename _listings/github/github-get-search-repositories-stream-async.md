---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/search/repositories
  scheme: https
  asyncapi_servers_variables:
    order:
      description: The sort field. if sort param is provided. Can be either asc or
        desc.
    q:
      description: |
        The search terms. This can be any combination of the supported repository
        search parameters:
        'Search In' Qualifies which fields are searched. With this qualifier you
        can restrict the search to just the repository name, description, readme,
        or any combination of these.
        'Size' Finds repositories that match a certain size (in kilobytes).
        'Forks' Filters repositories based on the number of forks, and/or whether
        forked repositories should be included in the results at all.
        'Created' and 'Last Updated' Filters repositories based on times of
        creation, or when they were last updated.
        'Users or Repositories' Limits searches to a specific user or repository.
        'Languages' Searches repositories based on the language they are written in.
        'Stars' Searches repositories based on the number of stars.
    sort:
      description: If not provided, results are sorted by best match.
    Accept:
      description: Is used to set specified media type.
    access_token:
      description: Your Github OAuth token.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search_repositories'
---
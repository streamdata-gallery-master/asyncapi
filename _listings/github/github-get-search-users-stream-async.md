---
version: 1.2.0
info:
  title: Github
  version: 1.2.0
servers:
- url: api.github.com/search/users
  scheme: https
  asyncapi_servers_variables:
    order:
      description: The sort field. if sort param is provided. Can be either asc or
        desc.
    q:
      description: |
        The search terms. This can be any combination of the supported user
        search parameters:
        'Search In' Qualifies which fields are searched. With this qualifier you
        can restrict the search to just the username, public email, full name,
        location, or any combination of these.
        'Repository count' Filters users based on the number of repositories they
        have.
        'Location' Filter users by the location indicated in their profile.
        'Language' Search for users that have repositories that match a certain
        language.
        'Created' Filter users based on when they joined.
        'Followers' Filter users based on the number of followers they have.
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
  - $ref: '#/components/messages/search_users'
---
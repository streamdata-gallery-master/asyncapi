---
version: 1.2.0
info:
  title: Spotify
  version: 1.2.0
servers:
- url: api.spotify.com/search
  scheme: https
  asyncapi_servers_variables:
    limit:
      description: The maximum number of items to return
    offset:
      description: The index of the first item to return
    q:
      description: 'The search query''s keywords (and optional field filters). The
        search is not case-sensitive: ''roadhouse'' will match ''Roadhouse'', ''roadHouse'',
        etc. Keywords will be matched in any order unless surrounded by quotes, thus
        q=roadhouse&20blues will match both ''Blues Roadhouse'' and ''Roadhouse of
        the Blues''. Quotation marks can be used to limit the match to a phrase: q=roadhouse&20blues
        will match ''My Roadhouse Blues'' but not ''Roadhouse of the Blues''. By default,
        results are returned when a match is found in any field of the target object
        type. Searches can be made more specific by specifying an album, artist or
        track field filter. For example q=album:gold%20artist:abba&type=album will
        search for albums with the text ''gold'' in the album name and the text ''abba''
        in an artist name. Other possible field filters, depending on object types
        being searched, include year, genre, upc, and isrc. For example, q=damian%20genre:reggae-pop&type=artist.
        The asterisk (*) character can, with some limitations, be used as a wildcard
        (maximum: 2 per query). It will match a variable number of non-white-space
        characters. It cannot be used in a quoted phrase, in a field filter, or as
        the first character of the keyword string. Searching for playlists will return
        results matching the playlist''s name and/or description.'
    type:
      description: A comma-separated list of item types to search across. Search results
        will include hits from all the specified item types; for example q=name:abacab&type=album,track
        will return both albums and tracks with "abacab" in their name.
    market:
      description: The market (an ISO 3166-1 alpha-2 country code).  If given, only
        items with content playable in that market will be returned.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/search'
---
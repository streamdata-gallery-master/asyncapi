---
version: 1.2.0
info:
  title: Stack Exchange
  version: 1.2.0
servers:
- url: api.stackexchange.com/posts
  scheme: https
  asyncapi_servers_variables:
    order:
      description: ""
    max:
      description: |
        sort = activity => date
        sort = creation => date
        sort = votes => number
    min:
      description: |
        sort = activity => date
        sort = creation => date
        sort = votes => number
    sort:
      description: ""
    fromdate:
      description: Unix date.
    todate:
      description: Unix date.
    pagesize:
      description: ""
    page:
      description: ""
    filter:
      description: |
        #Discussion

        The Stack Exchange API allows applications to exclude almost every field returned. For example, if an application did not care about a user's badge counts it could exclude user.badge_counts whenever it calls a method that returns users.

        An application excludes fields by creating a filter (via /filter/create) and passing it to a method in the filter parameter.

        Filters are immutable and non-expiring. An application can safely "bake in" any filters that are created, it is not necessary (or advisable) to create filters at runtime.

        The motivation for filters are several fold. Filters allow applications to reduce API responses to just the fields they are concerned with, saving bandwidth. With the list of fields an application is actually concerned with, the API can avoid unneccessary queries thereby decreasing response time (and reducing load on our infrastructure). Finally, filters allow us to be more conservative in what the API returns by default without a proliferation of parameters (as was seen with body, answers, and comments in the 1.x API family).

        #Safety

        Filters also carry a notion of safety, which is defined as follows. Any string returned as a result of an API call with a safe filter will be inline-able into HTML without script-injection concerns. That is to say, no additional sanitizing (encoding, HTML tag stripping, etc.) will be necessary on returned strings. Applications that wish to handle sanitizing themselves should create an unsafe filter. All filters are safe by default, under the assumption that double-encoding bugs are more desirable than script injections.

        Note that this does not mean that "safe" filter is mearly an "unsafe" one with all fields passed though UrlEncode(...). Many fields can and will contain HTML in all filter types (most notably, the *.body fields).

        When using unsafe filters, the API returns the highest fidelity data it can reasonably access for the given request. This means that in cases where the "safe" data is the only accessible data it will be returned even in "unsafe" filters. Notably the *.body fields are unchanged, as they are stored in that form. Fields that are unchanged between safe and unsafe filters are denoted in their types documentation.

        #Built In Filters

        The following filters are built in:

        default, each type documents which fields are returned under the default filter (for example, answers).
        withbody, which is default plus the *.body fields
        none, which is empty
        total, which includes just .total

        #Compatibility with V1.x

        For ease of transition from earlier API versions, the filters _b, _ba, _bc, _bca, _a, _ac, and _c are also built in. These are unsafe, and exclude a combination of question and answer body, comments, and answers so as to mimic the body, answers, and comments parameters that have been removed in V2.0. New applications should not use these filters.
    callback:
      description: |
        All API responses are JSON, we do support JSONP with the callback query parameter.
    site:
      description: |
        Each of these methods operates on a single site at a time, identified by the site parameter. This parameter can be the full domain name (ie. "stackoverflow.com"), or a short form identified by api_site_parameter on the site object.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/posts'
---
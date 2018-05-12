---
version: 1.2.0
info:
  title: Stripe
  version: 1.2.0
servers:
- url: api.stripe.com/orders
  scheme: https
  asyncapi_servers_variables:
    expand:
      description: Specifies which fields in the response should be expanded.
    created:
      description: Date this order was created.
    customer:
      description: Only return orders for the given customer.
    ending_before:
      description: A cursor for use in pagination. `ending_before` is an object ID
        that defines your place in the list. For instance, if you make a list request
        and receive 100 objects, starting with `obj_bar`, your subsequent call can
        include `ending_before=obj_bar` in order to fetch the previous page of the
        list.
    ids:
      description: Only return orders with the given IDs.
    limit:
      description: A limit on the number of objects to be returned. Limit can range
        between 1 and 100 items, and the default is 10 items.
    starting_after:
      description: A cursor for use in pagination. `starting_after` is an object ID
        that defines your place in the list. For instance, if you make a list request
        and receive 100 objects, ending with `obj_foo`, your subsequent call can include
        `starting_after=obj_foo` in order to fetch the next page of the list.
    status:
      description: Only return orders that have the given status. One of `created`,
        `paid`, `fulfilled`, or `refunded`.
    status_transitions:
      description: Filter orders based on when they were paid, fulfilled, canceled,
        or returned.
    upstream_ids:
      description: Only return orders with the given upstream order IDs.
stream:
  framing:
    type: chunked
    delimiter: \r\n
  read:
  - $ref: '#/components/messages/orders'
---
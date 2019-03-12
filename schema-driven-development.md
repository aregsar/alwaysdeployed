# Schema Driven Development

Is a concept that is similar to endpoint driven development in which the endpoint itself is static and the content of the message is the thing that determines the handler that generates the response and side effects of the request.

For GraphQL endpoints, each unique Query or Mutation message schema determines the endpoint handler that is dispatched to process the request.

For Realtime websocket endpoints, each unique topic channel or message type determines the endpoint handler that is dispatched to process the request.
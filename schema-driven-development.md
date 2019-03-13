# Schema Driven Development

Is a concept that is similar to [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development) in which the URI of the endpoint is static and instead the schema of the request data determines the handler that generates the response and side effects of the request.

Similar to endpoint driven development, the essence of schema driven development is that a user action triggers a request that contains a message type or schema instance, message resolvers that handle the message perform some function and returns a response to a user. That chain of events can be encapsulated as an atomic unit of a feature and developed, tested and deployed independently. 

Furthermore the process of developing a feature that corresponds to an independant message type or schema, from concept to production, meshes well with lean development practices and Kanban.

## GraphQL endpoints

For a GraphQL endpoint, each unique Query or Mutation message schema determines the endpoint handler that is dispatched to process the request.
So there will be a single `/graphql` endpoint URI that responds to each variation of the data with a independant response as a psudo endpoint.

## Websocket endpoints

For a Realtime Websocket endpoint, each unique channel and event message schema determines the endpoint handler that is dispatched to process the request.
So there will be a single `/socket` endpoint URI that responds to to each variation of the data with a independant response as a psudo endpoint.
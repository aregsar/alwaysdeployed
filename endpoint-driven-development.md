# Endpoint Driven Development


## In order to understand what is Endpoint Driven Development
it helps to define an endpoint by the following definitions:

-An endpoint corresponts to a URI that responds to an Http request with a
specific Http Verb.

-Each endpoint is a sub component of a feature, a microfeature.

-A feature is is an aggreagation of multiple endpoints


## Now that we have defined what an endpoint is, we can declare
the Endpoint Driven Development principles:

1-a specific handler or action is assoicated to single endpoint and will respond
to an Http request by producing a HttpResponse and possibly produces one or more
side effects such as updating a database, sending an email or adding a job to a queue

2-each endpoint is verified and guarded by a suit of endpoint tests that send Http requests
to the specific endpoint and validate responses and side effects.

3-Each endpoint is developed and deployed independantly and optionally guarded
by a feature flag

4-Once all endpoints of a feature are deployed the corresponding feature flag
for the feature is removed

5-Any changes to endpoint will result in a completely new version of the endpoint
(immutable endpoints) developed using the previous principles and guarded by a feature
change flag. After the the new version is deployed
the feature change flag and the old version of the endpoint will be removed.

6-Client side Ajax requests to an endpoint are part of a separate endpoint and not a part of
the reponse of another endpoint that included the Ajax client code.

7-Any middleware is considered a common endpoint and will be developed as
a stand alone endpoint.

8-Server side events that trigger realtime push notifications are considered side effects of handling an endpoint request.

## Special cases in Endpoint Driven Development

-Realtime endpoints

Realtime websocket endpoints use a single endpoint through which messages are exchanged based on the request message schema.
Therefore realtime endpoint development does not lend itself to endpoint driven development.
The reatime development process can be formalized using schema driven development.

-GraphQL endpoints

GraphQL endpoints use a single endpoint to service data queries and mutations based on the request message schema. 
Therefore GrapQL endpoint development does not lend itself to endpoint driven development.
The GraphQL development process can be formalized using schema driven development.


-Client side development

Client side development is inherently more complex and do not completely lend
themselved to endpoint driven development.
Their development process can be formalized under action driven development that
is similar in principal to endpoint driven development and is a work in progress.


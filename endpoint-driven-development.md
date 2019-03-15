# Endpoint Driven Development

Authored by: [Areg Sarkissian](https://aregsar.com/about)

Endpoint Driven Development is a methodology of web application development that enables granular feature functionality to be continuously integrated into a production application.

In Endpoint driven development an application is represented by a set of independant endpoints. Each endpoint represents a quantum of independant functionality that is aggregated with the rest of the endpoints to provide the full functionality of the application.

The process of developing and deploying independant endpoints, from concept to production, meshes well with lean development practices and Kanban.

The essence of endpoint driven development can be summed up as follows:

A user action triggers a request to an endpoint that performs some action and returns a response to the user. That chain of events can be encapsulated as an atomic unit of a feature and developed, tested and deployed independently.

## What constitutes an Endpoint?

It helps to define an endpoint using the following definitions:

- An endpoint corresponds to a URI that responds to an Http request with a
specific Http Verb.

- An endpoint responds to an Http request by returning a Http response and can possibly produce side effects as a consequence of the request.

- Each endpoint is a sub feature of a application feature.

- An application feature is an aggreagation of multiple endpoints.

## The principles of Endpoint Driven Development

- A specific handler assoicated to single endpoint will respond
to an Http request by producing a HttpResponse and possibly produce one or more
side effects such as updating a database, sending an email, adding a job to a queue or sending a websocket notification.

- Each endpoint is verified and guarded by a set of endpoint tests that send Http requests to the specific endpoint and validate responses and side effects.

- Each endpoint is developed and deployed independantly, optionally disabled
by a feature toggle until the set of endpoints that represent the feature are all deployed.

- Once all endpoints of a feature are deployed the corresponding feature toggle
for the feature can be removed. Feature toggles defined per feature, so multiple endpoints can be deployed under the same feature toggle.

- Deployed endpoints are immuatble so any changes to an endpoint will result in a completely new version of the endpoint. The versions of the endpoint can be switched by an endpoint toggle. After the new version is deployed the endpoint toggle and the old version of the endpoint can be removed.

- Client side Ajax requests to an endpoint are part of a separate endpoint request and not part of the reponse of another endpoint. So for example a request to an endpoint that returns a Html page is considered separate from the request to a different endpoint that an Ajax form on that page makes to submit the form.

- Any middleware is considered a common endpoint and will be developed as
a stand alone single endpoint feature.

- Server side events that trigger realtime push notifications are considered side effects of handling an endpoint request.

## Client side development - SPAs and Javascript Widgets

Endpoint driven development applies directly to REST and RPC style server side rendered web applications and web APIs.

Client side development is inherently more complex and does not lend itself to standard endpoint driven development principles.

The development process for client side applications can be formalized under [Action Driven Development](https://alwaysdeployed.com/action-driven-development) that is a superset of endpoint driven development better suited to developing client side applications, where each UI action corresponds to a psudo-endpoint.

An endpoint request, is a special case of a UI action, that is triggered by navigating to a URL, clicking a link, submitting a form or clicking an button that posts an Ajax request to an endpoint.

## Websocket endpoints

Realtime WebSockets use a single endpoint to process channel\event requests. Therefore realtime endpoint development does not lend itself to standard endpoint driven development principles.

The WebSocket development process can be formalized using [Schema Driven Development](https://alwaysdeployed.com/schema-driven-development) where a psudo-endpoint is defined based on the channel\event request message schema.

## GraphQL endpoints

GraphQL uses a single endpoint to process query\mutation requests.
Therefore GrapQL endpoint development does not lend itself to standard endpoint driven development principles.

The GraphQL development process can be formalized using [Schema Driven Development](https://alwaysdeployed.com/schema-driven-development) where a psudo-endpoint is defined based on the query\mutation request message schema.
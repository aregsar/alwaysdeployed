# Endpoint Driven Development

Endpoint Driven Development is a methodology of web application development that enables granular feature functionality to be continuously integrated into a production application.

In Endpoint driven development an application is represented by a set of independant endpoints. Each endpoint represents a quantum of independant functionality that is aggregated with the rest of the endpoints to provide the full functionality of the application.

The essence of endpoint driven development is that a user action triggers a request to an endpoint that performs some function and returns a response to a user. That chain of events can be encapsulated as an atomic unit of a feature and developed, tested and deployed independently. 

Furthermore the process of developing a feature that corresponds to an independant endpoint, from concept to production, meshes well with lean development practices and Kanban.

## What constitutes an Endpoint

It helps to define an endpoint using the following definitions:

- An endpoint corresponds to a URI that responds to an Http request with a
specific Http Verb.

- An endpoint responds to an Http request with a Http response and can possibly produce side effects as a consequence of the request.

- An aplication feature is is an aggreagation of multiple endpoints.

- Each endpoint is a sub component of a feature that we can call a sub feature.

## The principles of Endpoint Driven Development

- A specific handler or action is assoicated to single endpoint that will respond
to an Http request by producing a HttpResponse and possibly produces one or more
side effects such as updating a database, sending an email, adding a job to a queue or sending a websocket notification.

- Each endpoint is verified and guarded by a suit of endpoint tests that send Http requests to the specific endpoint and validate responses and side effects.

- Each endpoint is developed and deployed independantly, optionally disabled
by a feature toggle

- Once all endpoints of a feature are deployed the corresponding feature toggle
for the feature can be removed. Feature toggles are per feature so multiple endpoints can be deployed under the same feature toggle.

- Any changes to an endpoint will result in a completely new version of the endpoint
(immutable endpoints) developed using the previous principles and the versions can be switched by a feature change toggle. After the the new version is deployed
the feature change toggle and the old version of the endpoint can be removed.

- Client side Ajax requests to an endpoint are part of a separate endpoint request and not a part of the reponse of another endpoint. So for example a request to an endpoint that returns a Html page is considered separate from the request to an endpoint that an Ajax form on that page makes to submit the form.

- Any middleware is considered a common endpoint and will be developed as
a stand alone single endpoint feature.

- Server side events that trigger realtime push notifications are considered side effects of handling an endpoint request.

## Client side development - SPAs and Javascript Widgets

Endpoint driven development applies directly with REST and RPC style server side rendered web applications and web APIs.

Client side development is inherently more complex and does not completely lend
itself to standard endpoint driven development principles.

An endpoint request is a special case of an UI action, triggered by, navigating to a URL, clicking a link, submitting a form or clicking an button that posts an Ajax request to an endpoint.

The development process for client side applications can be formalized under [Action Driven Development](https://alwaysdeployed.com/action-driven-development/) that is a superset of Endpoint Driven development, which is better suited to client side applications and SPAs, where each UI action representing a psudo endpoint.

## Websocket endpoints

Realtime WebSockets use a single endpoint to process channel\event requests  
Therefore realtime endpoint development does not lend itself to standard endpoint driven development principles.
So instead a psudo endpoint is defined based on the channel\event request message schema.
The WebSocket development process can be formalized using [Schema Driven Development](https://alwaysdeployed.com/schema-driven-development/).

## GraphQL endpoints

GraphQL uses a single endpoint to process query\mutation requests.
Therefore GrapQL endpoint development does not lend itself to standard endpoint driven development principles.
So instead a psudo endpoint is defined based on the query\mutation request message schema.
The GraphQL development process can be formalized using [Schema Driven Development](https://alwaysdeployed.com/schema-driven-development/).
# Action Driven Development

Authored by: [Areg Sarkissian](https://aregsar.com/about)

Action driven development is a development process that is related to [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development) with the fundemental premiss that a UI action or a auto-action such as a timer expiration triggers an action event. This action event in turn changes the application state and possibly causes side effects such as making an ajax request to a URI endpoint. Upon changing of the application state, the UI is re-rendered producing a UI response.

Similar to [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development), the essence of action driven development is that a user action triggers a event that performs some function and returns a response to a user. That chain of events can be encapsulated as an atomic unit of a feature and developed, tested and deployed independently.

Furthermore the process of developing a feature that corresponds to an independant action, from concept to production, meshes well with lean development practices and Kanban.

Client side application development patterns such a `Redux`, which has the concept of Actions that trigger state change and side effects map well to action driven development.

> Note: The Action Driven Development formalization process is a work in progress.
# Always Deployed manifesto

The Always Deployed manifesto defines a process of web software development that helps development teams provide continuous value to customers from day one of a software project.

Furthermore it helps make the development process transparent to all stakeholders by providing continuous observabilty into the state of the application, starting from day one.

The Always deployed Manifesto adops the principle of [No Estimates](https://ronjeffries.com/xprog/articles/the-noestimates-movement/) to provide a real measure of development progress by allowing customers to litterally see an application come to life and evolve before their eyes.

Below are the three priciples of the Always deployed Manifesto:

## Application code should be deployed from day one

Projects should always be started by creating a new hello world project and committed into the master repository branch. The master branch should immediatly be deployed to a secure production environment.

## Deployed code should be monitored from day one

The deployed version of an application should include health check monitoring, error reporting, application metrics and logging starting from day one.
An Always Deployed application is not considerd deployed if it can't be monitored.

## Small Incremental changes should be continuously deployed to production

Application features should always be developed incrementally using [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development), with each endpoint controlled by a feature toggle.

Once an endpoints functionality is completely developed and the endpoint passes all endpoint tests it should be integrated into the master branch using [Trunk based development](https://trunkbaseddevelopment.com/).
The new version of the master branch should immediatly be deployed to the secure production environment.
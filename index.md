# Always Deployed manifesto

Authored by: [Areg Sarkissian](https://aregsar.com/about)

The Always Deployed manifesto defines a process of web software development that helps development teams provide continuous value to customers from day one of a software project.

Furthermore it helps make the development process transparent to all stakeholders by providing continuous observabilty into the state of the application, starting from day one.

The Always deployed Manifesto adops the principle of [No Estimates](https://ronjeffries.com/xprog/articles/the-noestimates-movement/) to provide a real measure of development progress by allowing customers to literally see an application come to life and evolve before their eyes.

The Always deployed Manifesto also adops the principle of [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development) to ensure that a deployed application is in a completed state at all times.

Below are the three priciples of the Always Deployed manifesto:

## Application code should be deployed to production from day one

Projects should be started by creating a new "hello world" project that is immediatly committed into the master repository branch.

The master branch should then immediatly be deployed to a secure production environment.

## Deployed production code should be monitored from day one

The production deployed version of an application should include health check monitoring, error reporting, application metrics and logging starting from day one.

An Always Deployed application is not considerd deployed if it can't be monitored.

## Small Incremental changes should be continuously deployed to production

Application features should always be developed and deployed incrementally using [Endpoint Driven Development](https://alwaysdeployed.com/endpoint-driven-development), with each deployed endpoint controlled by a feature toggle.

Once the endpoint functionality that is being developed is complete and the endpoint passes all endpoint tests, it should be integrated into the master branch using [Trunk based development](https://trunkbaseddevelopment.com/).

The new version of the master branch should immediatly be deployed to the secure production environment.
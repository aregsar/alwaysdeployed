# Always Deployed Manifesto

The Always Deployed manifesto is a process of software development that helps development teams provide continuous value to stakeholders from day one.

Furthermore it helps make the development process transparent to all stakeholders, by providing observabilty into the current state of the application.

Always deployed Manifesto adops the principles of NoEstimates to provide a real measure of development progress by leting customers litterally see an application come to life and evolve before their eyes.

Below are the three priciples of the Always deployed Manifesto:

## 1-Application code should be deployed from day one

We always start by creating a new hello world project and commit it to the master branch trunk based developonent and the code should immediatly be deployed to the production environment available under a custom domain name and the URI secured with SSL certificates.

## 2-Deployed code should be monitored from day one

The deployed hello world version of the application should include error reporting, 
health check monitoring, application metrics and logging starting from day one.
(Its not deployed unless it is monitored)

## 3-Small Incremental changes should be continuously deployed to production

Application features should always be developed incrementally using endpoint driven development, with each endpoint optionally hidden under a feature flag.

Once the endpoint functionality is complete and the endpoint passes all endpoint tests (integration tests are the true measure of a working application) it should be integrated into the master branch (using trunk based develpment) and the master branch should immidiatly be deployed to production.
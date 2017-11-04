# Santiment dev platform

This repository contains documentation of how apps for the santiment platform should be developed, so that we can plug them into our infrastructure.

## Backend

The santiment platform is language and data storage agnostic. You can develop backend services in any language, using any data storage, but you need to conform to certain conventions:

* Each service should contain a `Dockerfile` in its root folder, which builds a docker image that will allow to run the service. You can see an example `Dockerfile` here: https://github.com/santiment/sanbase2/blob/master/Dockerfile
* Each service shold provide a `Jenkinsfile` file, which describes how the project build is done. The build should run unit tests on the code and make sure all automatic checks are passing and if they do, build a docker image and push it to a central registry. You can see an example `Jenkinsfile` here: https://github.com/santiment/sanbase2/blob/master/Jenkinsfile
* Each service should be logging on the standard output, so that the platform can capture the logs and forward them to a standard log collection service

## Frontend

In santiment we are currently endorsing the React JS framework for building modular UI components. The components should follow certain conventions, so that they play nice with the rest of the UI:

* The components should try to be as dumb as possible and without side effects. Ideally the components should accept a number of parameters and render some content depending on these parameters. The side effects should be pushed up to the root page components.
* The CSS of the components should be scoped. We are currently using [styled-jsx](https://github.com/zeit/styled-jsx) for scoping the CSS. This provides CSS isolation and makes sure the CSS of component is not impacting the CSS of another component.

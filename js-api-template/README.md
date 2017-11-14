# Example NodeJS application

This is an example express application, which fit our deployment infrastructure.
It contains dockerfiles for building a production/staging image and for running
the tests. Also it contains a proper Jenkinsfile, which runs the tests and
builds images of the master branch when needed and pushes the images to an ECR.

To run the app do `node index.js`. It is preferred to split the logic of the app
in separate files and write tests for it in the `./test` folder.

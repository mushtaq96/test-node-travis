# node-docker

Simple node and express docker 
This project is a simple Node.js web application that uses MongoDB for storage. It is designed to be run as a Docker container.

## How to run

To run this application, you will need Docker installed on your machine. Once you have Docker installed, you can build the Docker image by running the following command in the project directory:

```
docker build -t myapp .
```

This will build a Docker image with the name `myapp`. Once the image has been built, you can run the application using the following command:

```
docker run -p 4000:4000 myapp
```

This will start the application and expose it on port 4000 of your machine. You can access the application by visiting `http://localhost:4000` in your web browser.

## Code explanation

The main code for the application is in the `index.js` file. This file sets up a simple Express server that listens on port 4000 and responds to requests with a JSON message.

The `MongoClient` is used to connect to a MongoDB database running on `localhost:27017`. Once the connection is established, the `db` object is used to interact with the database. In this case, the `collection` object is used to interact with the `documents` collection in the `testDB` database.

The `main` function is an `async` function that connects to the MongoDB database and returns a promise that resolves to the string `"done."`. This function is not currently used in the application, but it could be used for more complex initialization tasks.

## Continuous Integration

This project includes a `.travis.yml` file that defines a build configuration for Travis CI. Travis CI is a Continuous Integration (CI) service that automatically builds and tests code changes.

The `.travis.yml` file specifies that the build should be run on a Docker image with Node.js pre-installed. The build script then builds a Docker image for the application and runs a test suite.

Continuous Integration tools like Travis CI are useful for personal projects because they help ensure that changes to the codebase don't introduce new bugs or regressions. By automatically building and testing changes, developers can catch issues early and fix them before they become bigger problems.

## Comparison of Continuous Integration tools

Here's a comparison of three popular CI tools:

| Tool          | GitHub Actions | CircleCI | Travis CI   |
|---------------|----------------|----------|-------------|
| Pricing       | Free for public repositories | Free for limited usage, paid for more features | Free for open source, paid for private repositories and additional features |
| Configuration | YAML files in the repository | YAML files in the repository | YAML files in the repository |
| Scalability   | Built into GitHub, automatically scales | Automatically scales | Automatically scales |
| Integrations  | Integrated with GitHub | Integrates with GitHub, Bitbucket, GitLab | Integrates with GitHub, Bitbucket, GitLab, and more |

In general, these tools provide similar functionality and are all good choices for personal projects. The choice of tool may depend on factors like the existing toolset used in the project or the specific needs of the project.
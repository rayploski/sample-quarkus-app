# Sample Quarkus Application

This is a sample quarkus application used for various HashiCorp demos.

If you want to learn more about Quarkus, please visit its website: https://quarkus.io/ .

## Running the application in dev mode

You can run your application in dev mode that enables live coding using:
```shell script
./mvnw compile quarkus:dev
```

> **_NOTE:_**  Quarkus now ships with a Dev UI, which is available in dev mode only at http://localhost:8080/q/dev/.

## Packaging and running the application
Quite often one only needs to create a native Linux executable for their Quarkus application (for example in order to run in a containerized environment) and would like to avoid the trouble of installing the proper GraalVM version in order to accomplish this task (for example, in CI environments it’s common practice to install as little software as possible).

To this end, Quarkus provides a very convenient way of creating a native Linux executable by leveraging a container runtime such as Docker or podman. The easiest way of accomplishing this task is to execute:

The application can be packaged using:
```shell script
./mvnw install -Dnative -DskipTests -Dquarkus.native.container-build=true
```
Then, if you didn’t delete the generated native executable, you can build the docker image with:
```shell script
docker build -f src/main/docker/Dockerfile.native-micro -t rayploski/sample-quarkus-app .
```
And finally, run it with:
```shell script
docker run -i --rm -p 8080:8080 rayploski/sample-quarkus-app
```

If you want to learn more about building native executables, please consult https://quarkus.io/guides/maven-tooling.

## Provided Code

### RESTEasy Reactive

Easily start your Reactive RESTful Web Services

[Related guide section...](https://quarkus.io/guides/getting-started-reactive#reactive-jax-rs-resources)

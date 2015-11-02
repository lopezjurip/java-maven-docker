# Java Maven Docker
[![Build Status](https://travis-ci.org/mrpatiwi/java-maven-docker.svg)](https://travis-ci.org/mrpatiwi/java-maven-docker)

Simple dockerized Maven project with Java 8.


## Created with
```sh
mvn -B archetype:generate \
  -DarchetypeGroupId=org.apache.maven.archetypes \
  -DgroupId=com.mycompany.myapp \
  -DartifactId=myapp
```

## Getting Started

### Install dependencies
```sh
mvn install
```

### Run
```sh
mvn exec:java
```

## Docker

### Build
```sh
docker build --no-cache --rm --tag=myapp .
```

### Run
```sh
docker run --publish 4567:4567 --rm --name=myapp myapp mvn exec:java
```

## Using Docker-Compose

Inside `docker-compose.yml`:
```yml
myapp:
  build: .
  command: mvn exec:java
  ports:
    - "4567:4567"
```

Run it with:
```sh
docker-compose up -d
```

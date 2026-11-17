# Spring Boot Docker Practical

## Requirements
- Java 17
- Maven
- Docker Desktop (or a Docker-enabled environment)

## Run locally in VS Code terminal

```bash
mvn clean package -DskipTests
java -jar target/springboot-docker-0.0.1-SNAPSHOT.jar
```

Open http://localhost:8080 to verify the app. Stop it with Ctrl+C.

## Build the Docker image

```bash
docker build -t springboot-app .
docker images
```

## Run the container

```bash
docker run -d -p 8080:8080 --name spring-container springboot-app
```

## Verify

```bash
docker ps
docker logs spring-container
```

Open http://localhost:8080. Expected response:

`Spring Boot Application Running Successfully!`

## Stop and remove

```bash
docker stop spring-container
docker rm spring-container
```

If the container name is already in use, remove the old one first:

```bash
docker rm -f spring-container
```

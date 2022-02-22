# Todo-API based on Quarkus
This project uses Quarkus to provide a simple todo-app API. It implements an [OpenAPI spec](https://editor.swagger.io/?url=https://raw.githubusercontent.com/devshred/todo-api-spring-kotlin/main/src/main/resources/todo-spec.yaml) and can be tested with a [frontend based on Vue.js](https://github.com/devshred/todo-web).

## Deployment
Even though a shiny OpenShift Cluster waits for deployments, at the moment the deployment is based on Docker Compose.
```shell
docker compose -f src/main/docker/docker-compose.yaml up
```

## Dev environment
Starting frontend and backend in different terminals:
```shell
docker run --rm -p 8000:80 --name todo-web -e VUE_APP_API_BASE_URL=http://localhost:8080/api/v1/todo/ quay.io/johschmidtcc/todo-web
```
```shell script
./mvnw compile quarkus:dev
```
_(The app uses an in-memory H2 database.)_

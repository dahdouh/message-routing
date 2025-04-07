# Message routing application

This repository contains two submodules:

- backend(spring boot 3.4.4) available here https://github.com/dahdouh/backend
- frontend(angular 17) available here https://github.com/dahdouh/frontend

## Table of Contents

- Getting Started
  - Prerequisites
  - Installation
- Running the Project
- Postman collection

## Getting Started

To get a local copy of the project up and running, follow these steps.

### Prerequisites

- docker compose (v2.32.4 or later)

### Installation

1. Clone the repository:

```sh
git clone https://github.com/dahdouh/message-routing.git
```

2. Navigate to the project directory:

```sh
cd message-routing
```

3. download code of submodules:

```sh
git submodule update --init --recursive
```

4. access the submodule backend and build and generate jar file:

```sh
cd backend
mvn clean install -DskipTests

```
The tests are skipped because the are no ibmmq service started yet. So without message broker, some tests will failed. The ibmmq service will be started at next step (5)

5. Start different microservices, including ibmmq, backend,frontend:

- Go back to root project (message-routing witch contains docker-compose.yaml file)
```sh
cd ..
```

- Launch containers
```sh
docker-compose up
```

docker compose defines three services: ibmmq, backend, frontend

6. The application is available via
- UI: http://localhost:4200
  - administration credentials access:  username=`admin`, password=`admin`
- backend: http://localhost:8080

## Postman collection

In order to tests Rest endpoints of the backend microservice, a posmtan collection can be found on this link: https://github.com/dahdouh/message-routing/blob/master/message-routing.postman_collection.json
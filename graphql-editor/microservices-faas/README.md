---
description: >-
  Microservices allows to deploy back end code to our shared worker
  infrastructure
---

# Microservices FaaS

Microservices FaaS is a nodeJS service to run microservices inside GraphQL Editor Cloud. All microservices come with **MongoDB Serverless** included in the microservice. So together with microservice user receives a database.

### Getting Started

Shared worker deployments should be used in dev environments or MVP projects. They are limited to **200 requests per minute**. However, you can deploy microservices in your own infrastructure:\
\- All Docker/Kubernetes-based clusters.\
\- Azure Functions

#### Dev environment

GraphQL Editor CLI provides a local environment for your microservices if they live in the microservice cloud/ they are local/ live in the repository. With one simple command, it is possible to spin up the backend server.

#### MVP & PoC projects

GraphQL Editor Microservices combined with our **No-code Resolvers** can be the best option available on the market to build GraphQL backend in the shortest amount of time.

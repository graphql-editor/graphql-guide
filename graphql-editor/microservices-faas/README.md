---
description: >-
  Microservices allow you to deploy back end code to our shared worker
  infrastructure
---

# Microservices FaaS

Microservices FaaS is a nodeJS service to run microservices inside GraphQL Editor Cloud. All microservices come with **MongoDB Serverless** included in the microservice, so that together with a microservice user also receives a database.

### Getting Started

Shared worker deployments should be used in dev environments or MVP projects. They are limited to **200 requests per minute**. However, you can deploy microservices in your own infrastructure:\
\- All Docker/Kubernetes-based clusters\
\- Azure Functions

#### Dev environment

The GraphQL Editor CLI provides a local environment for your microservices if they live in the microservice cloud, are local or live in the repository. You can to spin up the backend server with one simple command.

#### MVP & PoC projects

GraphQL Editor Microservices combined with our **No-code Resolvers** may be the best option available on the market for building GraphQL backend in the shortest amount of time.

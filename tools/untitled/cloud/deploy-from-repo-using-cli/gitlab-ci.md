---
description: How to setup Gitlab CI with GraphQL Editor Shared worker deployment
---

# Gitlab CI

{% hint style="info" %}
To get GRAPHQL\__EDITOR\_TOKEN variable run the **token** command_
{% endhint %}

```yaml
image: node:14

stages:
  - deploy

deploy:
  only:
    - main
  stage: deploy
  variables:
    GRAPHQL_EDITOR_TOKEN: $GRAPHQL_EDITOR_TOKEN
  script:
    - npm i
    - |
      npx graphql-editor-cli deploy \
      -e SECRET_VALUE=$SECRET_VALUE 

```

---
description: GraphQL Cloud and instant Fake backend.
---

# Cloud

Our cloud GraphQL playground is vital for the one reason. Do not repeat yourself on testing APIs. So when you are working in a team it will help you collaborate.

Our faker engine is responsible for deploying fake GraphQL backend with a fake GraphiQL endpoint that you can use, e.g. in Front-end development. The fake endpoint also generates fake data based on types from the schema.

**To deploy faker you need a valid schema with at least a schema query type.** __ If you don't have it defined, the editor will throw an error when deploying it.

{% hint style="warning" %}
Remember. Your schema has to have a root query for GraphQL backends to work
{% endhint %}


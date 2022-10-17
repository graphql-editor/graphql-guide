---
description: Use gei integrations in your backend projects
---

# Installation

Installation is done via GraphQL Editor or just using an npm package name and providing resolver path to node\_modules path. The other way is to install it via GraphQL Editor

{% code title="package.json" %}
```json
{
  "dependencies": {
    "gei-crud": "0.0.2"
  }
}
```
{% endcode %}

{% code title="stucco.json" %}
```json
{
  "resolvers": {
    "Query.objects": {
      "resolve": {
        "name": "node_modules/gei-crud/lib/Query/objects"
      },
      "data": {
        "model": {
          "value": "Pizza"
        }
      }
    }
  }
}
```
{% endcode %}

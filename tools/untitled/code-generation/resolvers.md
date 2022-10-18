---
description: How to specify resolvers in a repo
---

# Resolvers

To specify resolvers in a repo use the CLI to add those with a command or manually edit the stucco.json file.

### Adding a resolver

```
npx gecli resolver
```

This above command will interactively ask you about what resolver code you want to create.

### Adding manually

Given that the `schema.graphql` in your repository looks something like this:

{% code title="schema.graphql" %}
```graphql
type Query{
    hello: String!
}

schema {
    query: Query
}
```
{% endcode %}

You can specify the resolver as follows. As you see the `name` is the path to a generated or `js` file.

{% code title="stucco.json" %}
```javascript
{
    "resolvers": {
        "Query.bundle": {
            "resolve": {
                "name": "lib/Query/hello"
            }
        }
    }
}
```
{% endcode %}

{% code title="hello.js" %}
```typescript
export const handler = () => "world"
```
{% endcode %}

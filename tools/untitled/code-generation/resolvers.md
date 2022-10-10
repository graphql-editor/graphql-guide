---
description: How to specify resolvers in repo
---

# Resolvers

To specify resolvers in repo use CLI to add those with a command or manually edit stucco.json file.

### Add a resolver

```
npx gecli resolver
```

This command will interactively ask you about what resolver code you want to create.

### Add manually

Given the `schema.graphql` in your repository looks like this:

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

You can specify the resolver as follows. As you see the `name` is the path to generated or `js` file.

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

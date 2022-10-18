---
description: GraphQL Field resolvers
---

# Resolvers

Resolvers are files or named exports.&#x20;

#### Default export

```typescript
export default (input) => {
    return  "Hello world"
}
```

#### Handler export

```typescript
export const handler = (input) => {
    return "Hello world"
}
```

#### Named export

```typescript
export const (input) => {
    return "Hello world"
}
```

```json
{
    "resolvers":{
        "RESOLVER_TYPE.RESOLVER_FIELD":{
            "resolve":{
                "name": "PATH_TO_RESOLVER.someName"
            }
        }
    }
}
```

#### Passing arguments to another resolver:



**Resolver "Query.todoOperations"**

{% code title="schema.graphql" %}
```graphql
type TodoOperations{
    getCreditCardNumber(id: String!): String
    showMeTehMoney: Int
}

type Query{
    todoOps: TodoOperations
}
```
{% endcode %}

{% code title="stucco.json" %}
```json
{
    "resolvers":{
        "Query.todoOps":{
            "resolve":{
                "name": "lib/todoOps"
            }
        },
        "TopoOps.getCreditCardNumber":{
            "resolve":{
                "name": "lib/getCreditCardNumber"
            }
        }
    }
}
```
{% endcode %}

``

{% code title="lib/todoOps.js" %}
```typescript
export default (input) => {
    return {
        creditCards:{
            dupa: "1234-1234-1234-1234",
            ddd: "1222-3332-3323-1233"
        }
    }
}
```
{% endcode %}

``

{% code title="lib/getCreditCardNumber.js" %}
```typescript
export default (input) => {
    const { id } = input.arguments
    return {
        response: input.source.creditCards[id]
    }
}
```
{% endcode %}

###

###

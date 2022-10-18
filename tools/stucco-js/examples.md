---
description: StuccoJS Examples
---

# Examples

This example shows a simple GraphQL schema with one string field resolver:

{% code title="schema.graphql" %}
```graphql
type Query{
    hello: String
}
schema{
    query: Query
}
```
{% endcode %}

{% code title="stucco.json" %}
```json
{
    "resolvers":{
        "Query.hello":{
            "resolve":{
                "name": "lib/hello"
            }
        }
    }
}
```
{% endcode %}

{% code title="hello.js" %}
```typescript
export function handler(input){
    return "Hello world"
}
```
{% endcode %}

When the following query is executed:

<pre class="language-graphql" data-title="GraphQL query"><code class="lang-graphql"><strong>{
</strong>    hello
}</code></pre>

It should yield this response:

{% code title="Response" %}
```json
{
    "hello": "Hello world"
}
```
{% endcode %}


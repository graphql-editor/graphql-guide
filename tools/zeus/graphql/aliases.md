---
link: graphql/aliases
title: Aliases
order: 3
category: GraphQL
---

# Aliases

Zeus also supports declaring aliases 🥸

```graphql
const aliasedQueryExecute = await chain('query')({
  listCards: {
    __alias: {
      atak: {
        attack: [
          { cardID: ['1'] },
          {
            name: true,
            description: true,
          },
        ],
      },
    },
  },
});
```

and here's the response:

```json
{
  "listCards": [
    {
      "atak": [
        {
          "name": "Zelma",
          "description": "Central"
        }
      ]
    }
  ]
}
```

Now you can access properties in a type-safe way by using:

```javascript
aliasedQueryExecute.listCards.map((c) => c.atak);
```

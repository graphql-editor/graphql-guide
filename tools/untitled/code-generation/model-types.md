---
description: Generate model types for popular databases like MongoDB
---

# Model Types

```bash
$ gecli codegen models
```

Generate TypeScript Models from GraphQL types. They are very handy to use with popular databases.

```graphql
type Person {
  firstName: String!
  lastName: String!
  email: String
  phone: String
  friends: [Person!]!
}
```

will be transformed to a model file

```typescript
import type { ModelTypes } from '@/zeus';
export type Person = ModelTypes['Person'];
```

later on you may want to transform it so that it is a database model

```typescript
import type { ModelTypes } from '@/zeus';
export type Person = Omit<ModelTypes['Person'], 'friends'> & {
  friends: string[];
};
```

You can see the concept.



**MongoDB**

Here is an example how you can use your model in MongoDB:

```typescript
db.collection<MyModel>.find({})
```

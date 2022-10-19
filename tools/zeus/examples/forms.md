---
link: forms
title: Forms
order: 1
category: Examples
---

# Forms

To use GraphQL Zeus with forms you should make use of its generated Value Types. When submitting a form using a mutation it is much easier and type-safe to do it using `ValueTypes`.

Here's an example schema:

```graphql
type Mutation {
  createUser(user: CreateUser!): String
}

input CreateUser {
  firstName: String!
  lastName: String!
  age: Int
  username: String!
}
```

You can use `ValueTypes['CreateUser']` as params for submit form function

```typescript
const submitForm = (values: ValueTypes['CreateUser']) => {
  // ..,rest of the code, validation
  return Chain('https://yourschemaurl.com/graphql', {
    headers: {
      Authorization: 'yourtoken',
    },
  })('mutation')({
    createUser: [{ user: values }, true],
  });
};
```

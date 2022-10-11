---
description: Tool to build forms and preview responses of GraphQL Resolvers
---

# GraphQL API Platform

Our API platform is only a better GraphiQL. The concept is the same, but it displays forms for inputs and data in tables. Every query can be saved to the GraphQL Editor Cloud the same way as the project schema is saved.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption></figcaption></figure>

### Adding Parameters

If query/mutation contains parameters they will be displayed as a form. This form can be filled in which provides a better experience to the user than the classical gql console.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption></figcaption></figure>

### Using widgets

Sometimes the type from GraphQL is not enough to provide the correct field to the user. Widgets provide different form fields for different situations.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption></figcaption></figure>

#### Date Widget

This widget provides the date and the datetime inputs formatted to the desired format

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Password Widget

Same as text but masks the input

#### Constant Widget

Always provide the same value for the field

#### Text field Widget

Same as text input, but with a configurable label and placeholder

#### Text box Widget

Display `textarea` instead of `input` for strings longer than `input` field

#### Relation Widget

This widget helps to display relations in your schema. So if you have to select one of the objects of type **A** in your form but you need to prefetch them you should use a relation widget. For example:

```graphql
type Query{
  itemsByPerson(person: String): [Item!]
  people: [Person!]
}
type Item{
  name: String;
  owner: Person;
}
type Person{
  name: String;
  items: [Item!];
}
```

So for itemsByPerson input, you set  `Query.people`as a helper to fetch People to select inside itemsByPerson&#x20;

#### Autocomplete Widget

Autocomplete widget is better for `String` completions like maps addresses.

#### Upload widget

This widget helps to upload the file through the standard S3 way.&#x20;

1. Perform a mutation to receive `putURL` `getURL` params
2. The widget will upload the file to the `putURL`&#x20;
3. It will return the file handle to the text input so it could be added to the object

---
description: Tool for building forms and previewing responses of GraphQL resolvers
---

# GraphQL API Platform

Our API platform is basically a richer GraphiQL. The concept is the same, but it displays forms for inputs and data in tables. Every query can be saved to the GraphQL Editor Cloud, the same way the project schema is saved.

<figure><img src="../../.gitbook/assets/image (5).png" alt=""><figcaption><p>response in table format</p></figcaption></figure>

### Adding Parameters

If a query/mutation contains parameters they will be displayed as a form. This form can be customized which provides a better experience to the user than the classical gql console.

<figure><img src="../../.gitbook/assets/image.png" alt=""><figcaption><p>write in or use dropdown to select parameters</p></figcaption></figure>

### Using widgets

Sometimes the type from GraphQL is not enough to provide the correct field to the user. Widgets provide different form fields for those situations.

<figure><img src="../../.gitbook/assets/image (19).png" alt=""><figcaption><p>use built-in widgets or import them from a library</p></figcaption></figure>

#### Date Widget

This widget provides the date and the datetime inputs formatted to the desired format.

<figure><img src="../../.gitbook/assets/image (1).png" alt=""><figcaption></figcaption></figure>

#### Password Widget

Same as text but masks the input.

#### Constant Widget

Always provides the same value for the field.

#### Text field Widget

Same as text input, but with a configurable label and placeholder.

#### Text box Widget

Displays `textarea` instead of `input` for strings longer than `input` field.

#### Relation Widget

This widget helps display relations in your schema. If for example, you have to select one of the objects of type **A** in your form but you need to prefetch them you should use a relation widget. For example:

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

So for `itemsByPerson` input, you set  `Query.people`as a helper to fetch People to select inside `itemsByPerson`.

#### Autocomplete Widget

Autocomplete widget is better for `String` completions such as map addresses.

#### Upload widget

This widget helps upload the file via the standard S3 way:&#x20;

1. Perform a mutation to receive `putURL` `getURL` params
2. The widget will upload the file to the `putURL`&#x20;
3. It will return the file handle to the text input so it can be added to the object

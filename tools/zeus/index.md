# GraphQL Zeus

Strongly Typed GraphQL from the team at [GraphQL Editor](https://graphqleditor.com/?utm_source=graphql_zeus_github)

GraphQL Zeus is the absolute best way to interact with your GraphQL endpoints in a type-safe way. Zeus uses your schema to generate Typescript types and strongly typed clients to unlock the power, efficiency, productivity and safety of Typescript on your GraphQL requests.

## Features

⚡️ Types mapped from your schema <br/>
⚡️ Works with Apollo Client, React Query, Stucco Subscriptions _(\*more coming soon...)_<br/>
⚡️ Works with Subscriptions <br/>
⚡️ Infer complex response types <br/>
⚡️ Create reusable selection sets (like fragments) for use across multiple queries <br/>
⚡️ Supports GraphQL Unions, Interfaces, Aliases and Variables<br/>
⚡️ Handles **massive** schemas <br/>
⚡️ Supports Browsers, Node.js and React Native in Javascript and Typescript <br/>
⚡️ Schema downloader <br/>
⚡️ JSON schema generation <br/>

## Generate Types With Zeus CLI Example

Simply run Zeus in your terminal to output your types file based on your graphql schema

![](/images/zeus-bash-command.png)

## Usage Example

Example using a generated `chain` client. Queries, mutations and subscriptions are now type-safe in arguments, field selections and response types.

![](/images/example.png)

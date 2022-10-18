---
description: Schema first GraphQL Server Library
---

# Stucco JS

### About

Stucco-js is JavaScript/TypeScript runtime for Stucco. It can be used as a local development environment or as a base library for implementing FaaS runtime.

### Configuration file

`Stucco-js` relies on [Stucco](https://github.com/graphql-editor/stucco) library written in GoLang. Configuration file format is in JSON.

#### Resolvers

```json
{
    "resolvers":{
        "RESOLVER_TYPE.RESOLVER_FIELD":{
            "resolve":{
                "name": "PATH_TO_RESOLVER"
            }
        }
    }
}
```

**Using TypeScript**

So if you have your TypeScript files in src folder you should transpile them to the lib folder and stucco can run it from there.

### Local development

To start local development you need `stucco.json`, `schema.graphql`, file with resolvers in the root folder and inside the root folder. To fetch your schema from the URL you can use a tool like [graphql-zeus](https://github.com/graphql-editor/graphql-zeus)

Add this script to your package json to test your backend

```
{
    "scripts":{
        "start": "stucco"
    }
}
```

Or run with npx

```
$ npx stucco
```

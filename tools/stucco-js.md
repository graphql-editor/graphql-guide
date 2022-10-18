---
description: Schema first GraphQL Server Library
---

# Stucco JS

### About

Stucco-js is a JavaScript/TypeScript runtime for Stucco. It can be used as a local development environment or as a base library for implementing a FaaS runtime.

### Configuration file

`Stucco-js` relies on the [Stucco](https://github.com/graphql-editor/stucco) library written in GoLang. The configuration file format is in JSON.

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

If you have your TypeScript files in the src folder you should transpile them to the lib folder and Stucco can run it from there.

### Local development

To start local development you need a folder with: `stucco.json`, `schema.graphql` and a file with resolvers in the root folder. To fetch your schema from the URL you can use a tool like [GraphQL-Zeus](https://github.com/graphql-editor/graphql-zeus).

Add this script to your package json to test your backend:

```
{
    "scripts":{
        "start": "stucco"
    }
}
```

or simply run with npx via:

```
$ npx stucco
```

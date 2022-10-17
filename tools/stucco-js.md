# Stucco JS

### About

Stucco-js is JavaScript/TypeScript runtime for Stucco. It can be used as a local development environment or as a base library for implementing FaaS runtime.

### Configuration file

`Stucco-js` relies on [Stucco](https://github.com/graphql-editor/stucco) library written in GoLang. Configuration file format is in JSON.

#### Resolvers

```
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

#### Custom Scalars

```
{
    "scalars":{
        "CUSTOM_SCALAR_NAME":{
            "parse":{
                "name": "PATH_TO_RESOLVER"
            },
            "serialize":{
                "name": "PATH_TO_RESOLVER"
            }
        }
    }
}
```

### Handler

You can also return Promise from handler

#### Default export

```
module.exports = (input) => {
    return  "Hello world"
}
```

#### Handler export

```
module.exports.handler = (input) => {
    return "Hello world"
}
```

#### Named export

```
module.exports.someName = (input) => {
    return "Hello world"
}
```

```
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

#### Passing arguments to another resolver



**Resolver "Query.todoOperations"**

```
type TodoOperations{
    getCreditCardNumber(id: String!): String
    showMeTehMoney: Int
}

type Query{
    todoOps: TodoOperations
}
```

```
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

`lib/todoOps.js`

```
module.exports = (input) => {
    return {
        response:{
            creditCards:{
                dupa: "1234-1234-1234-1234",
                ddd: "1222-3332-3323-1233"
            }
        }
    }
}
```

`lib/getCreditCardNumber.js`

```
module.exports = (input) => {
    const { id } = input.arguments
    return {
        response: input.source.creditCards[id]
    }
}
```

###

### Example



**Basic**

`schema.graphql`

```
type Query{
    hello: String
}
schema{
    query: Query
}
```

`stucco.json`

```
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

`lib/hello.js`

```
export function handler(input){
    return "Hello world"
}
```

`Test query`

```
{
    hello
}
```

```
{
    "hello": "Hello world"
}
```

This JSON defines resolver



**Using TypeScript**

So if you have your TypeScript files in src folder you should transpile them to the lib folder and stucco can run it from there.

###

### Local development

To start local development you need `stucco.json`, `schema.graphql`, file with resolvers in the root folder and inside root folder. To fetch your schema from URL you can use tool like [graphql-zeus](https://github.com/graphql-editor/graphql-zeus)

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
npx stucc
```

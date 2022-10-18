---
description: How to write resolvers for custom scalars
---

# Custom Scalars

Scalars used in your schema can be returned after being processed by a custom resolver function first. This is optional and by default, they are returned without a type check.

```json
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

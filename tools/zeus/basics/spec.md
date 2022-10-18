---
link: spec
title: Specification
order: 4
category: Basics
---

# Specification

Returned promise of type query data object:

```
PROMISE_RETURNING_OBJECT = Chain.[OPERATION_NAME]({
    ...FUNCTION_FIELD_PARAMS
})(
    ...QUERY_OBJECT
).then ( RESPONSE_OBJECT => RESPONSE_OBJECT[OPERATION_FIELD] )
```

Simple function params object:

```
FUNCTION_FIELD_PARAMS = {
  KEY: VALUE
}
```

Query object:

```
QUERY_OBJECT = {
    ...RETURN_PARAMS
}
```

Return params is an object containing RETURN\_KEY - true if it is a `scalar`, RETURN\_PARAMS for a `type` is otherwise a function where you pass field params and type return params.

```
RETURN_PARAMS = {
    RETURN_KEY: true,
    RETURN_KEY: {
        ...RETURN_PARAMS
    },
    RETURN_FUNCTION_KEY:[
        {
            ...FUNCTION_FIELD_PARAMS
        },
        {
            ...RETURN_PARAMS
        }
    ]
}
```

## Use Alias Spec

```
RETURN_PARAMS = {
  __alias: RETURN_PARAMS
}
```

Access aliased operation in a type-safe way

```
PROMISE_RETURNING_OBJECT[ALIAS_STRING]
```

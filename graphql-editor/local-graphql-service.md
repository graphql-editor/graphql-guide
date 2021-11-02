---
description: How to run local server
---

# Local GraphQL Server

stucco server can be run locally and inside docker. To run a local GraphQL server you need to have some resolvers and code.&#x20;

{% hint style="info" %}
If you are using TypeScript remember to build the code first.
{% endhint %}

{% code title="package.json" %}
```json
{
    "scripts":{
        "start": "stucco"
    }
}
```
{% endcode %}

to start a server

```shell
$ npm run start
```

You will get lthe ocal server running on 8080 port.

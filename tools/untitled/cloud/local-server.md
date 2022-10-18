---
description: Local server for cloud files
---

# Local server

When you have a microservice in the cloud with or without GraphQL Editor backend, you can run a local GraphQL server for your microservice by using the following command:

```
npx gecli cloud server
```

This command will

1. Download your files from GraphQL Editor Cloud to a temporary folder
2. Install packages inside the folder
3. Run `stucco` server and typescript server inside that folder

This command will also react to the changes made inside GraphQL Editor.&#x20;

This is simply the fastest way to spin a local server for your no-code GraphQL Editor system.

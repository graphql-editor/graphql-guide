---
description: Create your own no-code integrations
---

# Develop own integrations

**Development**

To develop GraphQL Editor integration use `gecli create backend` command to create your project. Then initialize the integration.

**Data format**

{% code title="integration.ts" %}
```typescript
type IntegrationData = {
  name: string;
  description: string;
  value: string | string[];
  required?: boolean;
};

type IntegrationSpecification = {
  [resolver: string]: {
    name: string;
    description: string;
    data: Record<string, IntegrationData>;
    resolve: { name: string };
  };
};
const integration: IntegrationSpecification = {
  'Query.objects': {
    name: 'List objects',
    description: 'List objects stored in database',
    data: {
      model: {
        name: 'Database model',
        description: 'Specify model name',
        value: 'Object',
        required: true,
      },
      sourceFilterParameters,
    },
    resolve: {
      name: 'lib/Query/objects',
    },
  },
};
```
{% endcode %}

Later on after `gecli gei integrate` command it integrates your typescript file to the `stucco.json`

**Init**

Init files needed to create integration from your backend project to be used in GraphQL Editor No-Code editor or as npm package.

**Integrate**

Integrate your files with project's `stucco.json`

**Publish**

Publish your integration to GraphQL Editor be used in GraphQL Editor No-Code editor.

**Unpublish**

Unpublish your integration from GraphQL Editor

---
description: The best way to connect GraphQL schemas
---

# Schema Libraries

Schema libraries allow you to import one schema to another. You cannot see the imported nodes directly in the code editor but you can see them in the Graph view, from where you can inject them into your schema. Imported Graph library nodes are marked with a dashed line.

<figure><img src="../.gitbook/assets/image (1) (2).png" alt=""><figcaption></figcaption></figure>

Every GraphQL Editor project can act as a library, we just need to cut off the schema keyword. Library nodes are not editable. To edit libraries you should either extend library nodes or edit the library project directly and release a new version.

### Attaching libraries to an existing project

To attach libraries to an existing project click **Libraries** in the top menu, it will take you to the libraries screen.

<figure><img src="../.gitbook/assets/image (7) (3).png" alt=""><figcaption></figcaption></figure>

You can choose one of our common libraries or search your workspaces for libraries to add. To attach a library simply click the **+** button next to it. You can also change the version of the library by using the dropdown menu on the right side of the panel.

{% hint style="success" %}
Remember to press **save changes** when you are done editing!
{% endhint %}

---
description: The best way to connect GraphQL schemas
---

# Schema Libraries

Schema libraries allow you to import one schema to another. You cannot see the imported nodes directly in the code editor but you can see them in the Graph view from where you can inject them into your schema. Imported Graph library nodes are marked with a dashed line.

![](<../.gitbook/assets/image (11).png>)

Every GraphQL Editor project can act as a library. We just cut off the schema keyword. Library nodes are not editable. To edit libraries you should either extend library nodes or edit the library project directly and release a new version.

### Attaching libraries to an existing project

To attach libraries to an existing project click **Edit GraphQL libraries**.

The library screen will popup

![](<../.gitbook/assets/image (10) (1).png>)

To attach a library, search for it and click the small tick. You can also change the version of the library by clicking a suitable version on the right side of the panel.

{% hint style="success" %}
Remember to click the **save** button when you are done editing to accept changes!
{% endhint %}

### Add libraries when creating a project

To add libraries to a new project, simply click add libraries checkbox during the project creation process, search for the libraries, and select them.

![](<../.gitbook/assets/image (3).png>)

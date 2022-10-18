---
description: How to browse complex GraphQL Schemas
---

# ERD like Relation View

Navigating a big GraphQL Schema with only code is nearly impossible. Instead use our diagram view to see how to browse it in an easy and transparent way.

<figure><img src="../../.gitbook/assets/relation_view(18).png" alt=""><figcaption><p>Example ERD relation view exported to .png</p></figcaption></figure>

### Navigation

Navigate through this view, click to center on a node and see all its relations displayed.

### Search & Order

Searching and ordering is available inside the top bar:

<figure><img src="../../.gitbook/assets/image (2) (2).png" alt=""><figcaption></figcaption></figure>

After searching you will get only the nodes from the search. Ordering is used to switch the order of Type Definitions like `type` `scalar` `interface` `enum` `input` `union`.

### Node options

Additional options are available after selecting a node:

<figure><img src="../../.gitbook/assets/image (2).png" alt=""><figcaption></figcaption></figure>

#### Parent

Display parent relations: show where this node is used. Turn off to only display children relations.

#### Scalars

Display/hide base scalar fields including `String`, `Int`, `Float`, `ID`, `Boolean`.

#### Enums

Expand/hide all enums. Enums can be tricky as the localization enum can consist of hundreds of values.

#### Deselect node

Deselect active node

#### Focus node&#x20;

Scrolls the node to the center of the current view.

#### Export to PNG

Exports current relation nodes to a png file.

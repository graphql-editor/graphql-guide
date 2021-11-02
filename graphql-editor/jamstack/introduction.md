---
description: Great way to play with data from GraphQL backend.
---

# GraphQL based pages

You can create fully functional static GraphQL data-driven websites using our JAMStack Tool. The websites are entirely based on your schema and customisable using CSS and JS consoles. You also have an option to preview, export and save your work in a few convenient ways.

![](<../../.gitbook/assets/image (2).png>)



### Creating a static page preview

Now you can start writing the CSS/JS code that will describe how your frontend will look like. If you want to change the endpoint you are calling for this schema (for example real backend), just change this function a little bit. See the example of the entire code [here](https://nightly.graphqleditor.com/stack-of-the-future/pokemon?visibleMenu=mock).

```javascript
export default async () => {
    const Fetch = Chain("https://graphql-pokemon2.vercel.app/", {
        "Content-Type": "application/json"
    })
    const response = await Fetch.query({
        pokemons: [{ first: 151 }, {
            number: true,
            name: true,
            image: true,
            types: true,
            resistant: true,
            weaknesses: true
        }]
    })
    const app = html`<${App} response=${response} />`
    return r(app)
}
```

This is driven by GraphQL Zeus:

{% embed url="https://github.com/graphql-editor/graphql-zeus" %}

Zeus is a GraphQL client for Javascript and TypeScript. For more information read the [GraphQL Zeus readme](https://github.com/graphql-editor/graphql-zeus/blob/master/README.md) on github.

Here, we copied our pre-made CSS code with the following result:

After changing the JS code, update it by clicking the green play button or by Cmd/Crtl + S to see the results in the preview on the right.

### Preview and download&#x20;

Finally, we added a few ways to display and export the result of your work:

* by clicking the **purple eye button**, you can preview the mock frontend in a new tab
* you can **Deploy a static site** - this will generate a website viewable online - to access it click **Open deployed static site**
* **Export zipped static site **will download all of your mock frontend as JSON, CSS, and JS files in one zip folder

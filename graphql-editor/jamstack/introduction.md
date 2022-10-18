---
description: A visual way to play with data from a GraphQL backend.
---

# JS Playground

You can create fully functional static GraphQL data-driven websites using our JAMStack Tool. The websites are entirely based on your schema and customizable using CSS and JS consoles. You also have an option to preview, export and save your work in a few convenient ways.

<figure><img src="../../.gitbook/assets/jsplayground production.gif" alt=""><figcaption><p>JS Playground in action</p></figcaption></figure>

### Creating a static page preview

You can immediately start writing the CSS/JS code that will describe how your front-end will look like. If you want to change the endpoint you are calling for this schema (for example to a real backend) just change this function a little bit.

```typescript
import React, { useEffect } from 'https://cdn.skypack.dev/react@17.0.2';
import ReactDOM from 'https://cdn.skypack.dev/react-dom@17.0.2';

const MainComponent: React.FC = ({ children }) => {
    return <div style={{
        background: '#fff',
        padding: 10
    }}>
        <div className="is-size-4 mb-4">Pizza pizza</div>
        {children}
    </div>
}

const PizzaSelector = Selector('Pizza')({
    name: true,
    description: true,
    ingredients: {
        name: true
    },
    price: true,
})

type PizzaType = FromSelector<typeof PizzaSelector,'Pizza'>

const Pizza: React.FC<PizzaType> = ({ name, ingredients, price,description }) => {
    return <div className="box">
        <div className="block"><strong className="mr-4">{name}</strong><i>{new Intl.NumberFormat('de-DE', { style: 'currency', currency: 'EUR' }).format(price)}</i></div>
        <div className="block">{description}</div>
        <div className="tags">
            {ingredients.map(i => <div className="tag">{i.name}</div>)}
        </div>
    </div>
}

export const data = async () => {
    const queryFetch = Gql("query")
    const result = await queryFetch({
        menu: {
            pizzas: PizzaSelector
        }
    })
    return result.menu.pizzas
}



type DataType = ReturnType<typeof data> extends Promise<infer R> ? R : ReturnType<typeof data>

export default (props: DataType) => {
    return <MainComponent>{props.map(Pizza)}</MainComponent>
}
```

JS Playground is driven by GraphQL Zeus:

{% embed url="https://github.com/graphql-editor/graphql-zeus" %}

Zeus is a GraphQL client for Javascript and TypeScript. For more information read the [GraphQL Zeus readme](https://github.com/graphql-editor/graphql-zeus/blob/master/README.md) on GitHub.

After changing the JS code, update it by clicking the play button or by Cmd/Crtl + S to see the results in the preview window on the right.

### Preview and download&#x20;

Additionally we added a few ways to display and export the result of your work:

* by clicking the **eye button**, you can preview the mock front end in a new tab
* **Export zipped static site** will download all of your mock front-end as JSON, CSS, and JS files in one zip folder

# Layout component

Layout components which also are business agnostic and that aim to give shapes for your pages.

```ts
export const Card: FunctionComponent<Props> = ({ title } => {
    const today = new Date
    return (
        <View>Title: {title}</View>
        <View>Date: {today}</View>
    )
})
```
**<font color=red>The component should NOT be connected to the store.</font>**

### Export
Any declaration (such as variable, function, enum, types) can be exported.
```ts
export interface Model {
    id: string
}
```
### Import
Import is about as export from a module. 
```ts
// good
import { Model } from './model'

// bad
import * as Models from './model'
```
**<font color=red>Avoid to using import with `*`. It might be increeases the bundle size.</font>**

### Assign Unique Key to each Element
In React native assigning a unique key can solve many issues that make it harder to work with applications containing components such as Lists 
```ts
const commentItems = comments.map((comment) => 
    <Item key={commnet.id}>
        {comment.name}
    </Item>
);
```
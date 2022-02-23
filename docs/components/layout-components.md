# Layout component

Layout components which also are business agnostic and that aim to give shapes for your pages.

```tsx
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
```tsx
export interface Model {
    id: string
}
```
### Import
Import is about as export from a module. 
```tsx
// good
import { Model } from './model'

// bad
import * as Models from './model'
```
**<font color=red>Avoid to using import with `*`. It might be increeases the bundle size.</font>**
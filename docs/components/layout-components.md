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
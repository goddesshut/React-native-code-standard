# Functional components

They are the simplest way to define components:
```tsx
import React, { FunctionComponent } from 'react'
export const Home: FunctionComponent<Props> = ({ route, navigation }) => {
    return (
        <View>Hello World</View>
    )
}
```
### Benefits

- Small
- Easy to build & read

### Drawbacks

- Can't old state (at least before React 16.8)
- Don't have lifecycle methods (at least before React 16.8)
- **Rerender everytime a parent is modified**

### Component update

While dealing with `memo` or `PureComponent` , it's important to remember that anonymous function or objects while always cause a rerender.

When React wants to verify that a component has changed, it will first compare its **actual props and its previous props**. If they differ at anylevel, the component will rerender.

The problem with anonymous functions / objects is that the reference changes between two renders: the function / object is **redefined** each time:

```javascript
(() => 3) !== (() => 3); // true
```

To tackle this problem in the simplest possible way, we can name functions:

```javascript
const isThree = () => 3;
isThree !== isThree; // false
```

And it's also more readable and provide a useful name for further use ;)


### Higher Order Component (HOC)
A higher order componentis a function that takes a componet and return a new component.
Let's think of it just like an Higher Order Function, but with component. The idea is to call a function by passing it a Component definition as argument. Imagine the following logger
```tsx
export const Home: FunctionComponent<Props> = ({ route, navigation }) => {
    const Children = ({ positionX, positionY }) => // some implementation details

    const ScrollableChildren = withScroll(Children);

    return (
        <ScrollHandler>
            <ScrollableChildren /> {/* the children owns the positionX and positionY ! */}
        </ScrollHandler>
    )
}
```
As you may have seen, the idea is to put a wrapper around the component to simulate some enhancements over it. The withLogger function can now be called at multiple places and is a great way to make code reusable.
# Functional components

They are the simplest way to define components:

```tsx
const User = ({ firstName }) => <div>Hello {firstName}</div>;
```

## Benefits

- Small
- Easy to build & read

## Drawbacks

- Can't old state (at least before React 16.8)
- Don't have lifecycle methods (at least before React 16.8)
- **Rerender everytime a parent is modified**

## Tips

- In React 16.6, `memo` is coming an allows to shallow compare props (same as [Pure components](#pure-components))
- Keep them close to the end of the tree, I mean it's better to put them as leaf in the tree

# Component update

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
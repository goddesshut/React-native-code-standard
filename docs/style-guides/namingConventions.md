# Naming conventions

### Project respository

- Every folder under "src" start with a lowercase letter.
>  Example
> - components, screens, utils

- Every folder under "screens" & "component" starts with an uppercase letter and have a max of 3 words to describe it.
>  Example
> - HomeScreen.tsx, SummaryCard.tsx, Home, Watchlist, CustomButton

- Every file in the project starts with a lowercase letter. 
>  Example
> - index.ts, home.ts, currency.ts


### Coding
- **Variables** starts with a lowercase letter and have a max of 3 words to describe them.
- **Constants** starts with a lowercase letter and have a max of 3 words to describe them.

**Function**
- Private function will start with a lowercase letter as normal just put private to define type of funtion.
- Public function will start with a lowercase letter.
``` tsx
private goToScreen = () => {}; // Private funtion
goToScreen = () =>  {} // Public function
```

### Props
Always use camelCase for prop names, or PascalCase if the prop value is a React component.
``` tsx
// bad
<Home
  UserName="hello"
  phone_number={12345678}
/>

// good
<Home
  userName="hello"  //props string
  phoneNumber={12345678}  //prop number
  Component={SomeComponent} //prop component
/>
```


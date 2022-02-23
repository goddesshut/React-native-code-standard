# Hooks

Hooks are the new thing in React and are arriving with React 16.8. They aim to provide more functionalities to functional components and they also provide a way to encapsulate some logic outside the components to be able to reuse them.

``` tsx
enum HomeTypes {
    FETCH_HOME = "fetchHomeService"
}

const useHome = () => {
    return useQuery(HomeTypes.FETCH_HOME, () => fetchData())
}

const Parent = () => {
  const home = useHome(); // this is a reusable hook

  return <Children data={useHome.data} />;
};
```
# TanStack Query Dev Tools (FKA React Query)

![react-query](https://repository-images.githubusercontent.com/207645083/e5281400-c0a4-11ea-911e-bf5e8aee9f15)

***Topics***

- React Query Overview
- React Query Basics
- React Query data states
- React Query Dev tools

## React Query Overview

React Query is a powerful library for managing server state in React applications. It provides tools to fetch, cache, and update data in your React components, making it easier to handle asynchronous data fetching and synchronization with your backend.

Here's a breakdown of what React Query offers and how it works:

**Data Fetching**: React Query simplifies the process of fetching data from APIs. It handles loading and error states, eliminating the need for manual management of these states in your application.

**Caching**: The library automatically caches responses, which improves performance. When a query is repeated, React Query first checks the cache and returns cached data if available. This reduces unnecessary network requests.

**Background Updates**: React Query can refetch data in the background to keep the user interface up-to-date with the latest data. This ensures that the data displayed is as fresh as possible without any manual intervention.

**Automatic Refetching**: React Query can be configured to automatically refetch data under certain conditions, like when the window regains focus or when the network connection is restored.

**Query Invalidation and Dependent Queries**: It allows you to invalidate queries, which is useful when related data changes and needs to be refetched. You can also define dependent queries that only run after certain conditions are met.

**Pagination and Infinite Queries**: React Query supports complex features like pagination and infinite scrolling out of the box. It provides hooks that make implementing these features much simpler.

**Optimistic Updates**: The library supports optimistic updates, where you can update the UI optimistically before the server response arrives. This makes the application feel faster and more responsive.

**Built-in Devtools**: React Query comes with built-in devtools that provide insight into queries and their states, making debugging easier.


## React Query Basics

pre-recs:
We should understand the Query states that we have in React Query


What is a Query?

  - A query is a declarative dependency on an asynchronous source of data that is tied to a unique key. A query can be used with any Promise based method (including GET and POST methods) to fetch data from a server. If your method modifies data on the server, we recommend using Mutations instead.

  - To subscribe to a query in your components or custom hooks(HINT: ***WE SHOULD DO THIS***), call the useQuery hook with at least:

  1. A unique key for the query
  2. A function that returns a promise that:
       - Resolves the data, or
       - Throws an error

```tsx
  export const useMicroservice = () => {
    const results = useQuery({
      // Query Key, a unique id that can be called anywhere in our app.
      // using hooks like useQueryClient will give us a way to view the data cached
      // with the query key. We do not always need to call this hook to view that data
      queryKey: ["my-query-key"]
      mutationFn: () => Promise.resolve([{title: "some title", body: "some body"}])
    })

    return {...results }
  }
```

#### Thing to be aware of

1. when using useMicroservice in a component during the componentDidMount portion of the lifecycle if the data save with the queryKey is either invalid or stale it will fire the GET request to bring the data back to a

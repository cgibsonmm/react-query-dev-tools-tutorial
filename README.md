# TanStack Query Dev Tools (FKA React Query)

![react-query](https://repository-images.githubusercontent.com/207645083/e5281400-c0a4-11ea-911e-bf5e8aee9f15)

***Topics***

- React Query Basics
- React Query data states
- React Query Dev tools

## React Query Basics

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

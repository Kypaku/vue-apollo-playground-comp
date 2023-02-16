# vue-apollo-playground-comp
A simple playground for Apollo Client

# Vue Apollo Playground Component
A simple Vue component for testing GraphQL queries and mutations with Apollo Client.

# Installation
To use this component in your Vue project, install it via npm:
The omponent uses Vue 3

# Usage
```js
import { ApolloPlayground } from './destination-folder';
```
Use the component in your template:
```html
<template>
  <ApolloPlayground :apolloClient="apolloClient" />
</template>
```

Available props:
apolloClient: Your apollo client. The field is required.


# vue-apollo-playground-comp
A simple playground for Apollo Client

# Vue Apollo Playground Component
A simple Vue component for testing GraphQL queries and mutations with Apollo Client.

# Installation
To use this component in your Vue project, install it via npm:
The omponent uses Vue 3

![Preview](https://downloader.disk.yandex.ru/preview/6e7af9c760c4a49335d0bae79a283463e4e015e1beea85c6ff2b68ff27b29032/63eeb2aa/6oYwJpwMSNyzaF7zDR5sObqkzWRu3-utrL_4VJ9Wi58dGQV6stxO1HaE5gE2OzBAggjxyXQASoJiVJ3zhKXgPQ%3D%3D?uid=0&filename=2023-02-16_21-47-02.png&disposition=inline&hash=&limit=0&content_type=image%2Fpng&owner_uid=0&tknv=v2&size=2048x2048)

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


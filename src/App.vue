<template>
    <header>
      <headerVue />
      <mainVue />
    </header>
  </template>
  
  <script>
  import HeaderVue from "./components/header.vue";
import mainVue from './components/main.vue';

  
  export default {
    name: "App",
    components: {
      HeaderVue,
      mainVue
    },
  };
  </script>
  
  <style scoped></style>
  
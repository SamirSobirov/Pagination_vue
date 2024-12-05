<template>
    <header>
      <headerVue />
    </header>
  </template>
  
  <script>
  import HeaderVue from "./components/header.vue";
  
  export default {
    name: "App",
    components: {
      HeaderVue,
    },
  };
  </script>
  
  <style scoped></style>
  
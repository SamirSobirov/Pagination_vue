<template>
  <header>
    <headerVue />

<aviaInputs/>
    <div class="flex items-center justify-center gap-8">

      <mainVue />
      <tableVue />
    </div>
  </header>
</template>

<script>
import HeaderVue from "./components/header.vue";
import mainVue from "./components/main.vue";
import tableVue from "./components/table.vue";
import aviaInputs from "./components/aviaInputs.vue";

export default {
  name: "App",
  components: {
    HeaderVue,
    mainVue,
    tableVue,
    aviaInputs
  },
};
</script>

<style scoped></style>




<template>
  <div id="app">
    <MainContent />
  </div>
</template>

<script>
import MainContent from "./components/MainContent.vue";

export default {
  name: "App",
  components: {
    MainContent,
  },
};
</script>

<style lang="scss">
* {
  margin: 0;
  padding: 0;
  box-sizing: border-box;
  font-family: sans-serif;
}

body {
  background-color: #1e2d3b;
  padding: 3rem 0;
}
</style>

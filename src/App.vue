<template>
  <div id="app">
    <MainHeader @onSelectChange="searchRecord" />
    <MainContent :genre="input" />
  </div>
</template>

<script>
import MainContent from "./components/MainContent.vue";
import MainHeader from "./components/MainHeader.vue";

export default {
  name: "App",

  data() {
    return {
      input: "",
    };
  },

  components: {
    MainContent,
    MainHeader,
  },

  methods: {
    searchRecord(data) {
      return (this.input = data);
    },
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

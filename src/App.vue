<template>
  <div id="app">
    <MainHeader @onSelectChange="filteredRecord" />
    <MainContent :records="filteredRecords" />
  </div>
</template>

<script>
import MainContent from "./components/MainContent.vue";
import MainHeader from "./components/MainHeader.vue";
import axios from "axios";

export default {
  name: "App",
  data() {
    return {
      records: [],
    };
  },

  computed: {
    filteredRecords(input) {
      return this.records.filter(
        (record) => record.genre.toLowerCase() === input
      );
    },
  },

  methods: {
    getRecords() {
      axios
        .get("https://flynn.boolean.careers/exercises/api/array/music")
        .then((response) => {
          this.records.push(...response.data.response);
        });
    },
  },
  mounted() {
    this.getRecords();
  },

  components: {
    MainContent,
    MainHeader,
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

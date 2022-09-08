<template>
  <div id="app">
    <MainHeader @onGenreChange="getGenre" @onAuthorChange="getAuthor" />
    <MainContent :genre="genre" :author="author" />
  </div>
</template>

<script>
import MainContent from "./components/MainContent.vue";
import MainHeader from "./components/MainHeader.vue";

export default {
  name: "App",

  data() {
    return {
      genre: "",
      author: "",
    };
  },

  components: {
    MainContent,
    MainHeader,
  },

  methods: {
    getGenre(data) {
      return (this.genre = data);
    },

    getAuthor(data) {
      return (this.author = data);
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

<template>
  <div>
    <select
      name="genre"
      id="music-genre"
      v-model="selectedGenre"
      @change="$emit('onGenreChange', selectedGenre)"
    >
      <option value="">Seleziona un genere</option>
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>

    <select
      name="author"
      id="author"
      v-model="selectedAuthor"
      @change="$emit('onAuthorChange', selectedAuthor)"
    >
      <option value="">Seleziona un autore</option>
      <option value="bonjovi">Bon Jovi</option>
      <option value="queen">Queen</option>
      <option value="sting">Sting</option>
      <option value="stevegaddband">Steve Gadd Band</option>
      <option value="ironmaiden">Iron Maiden</option>
      <option value="ericclapton">Eric Clapton</option>
      <option value="deeppurple">Deep Purple</option>
      <option value="metallica">Metallica</option>
      <option value="daveweckl">Dave Weckl</option>
      <option value="michaeljacjson">Michael Jacjson</option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      selectedGenre: "",
      selectedAuthor: "",
    };
  },
};
</script>

<style lang="scss" scoped></style>

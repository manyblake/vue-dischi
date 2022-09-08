<template>
  <div>
    <select
      name="genre"
      id="music-genre"
      v-model="inputSearch"
      @change="$emit('onSelectChange', inputSearch)"
    >
      <option value="rock">Rock</option>
      <option value="pop">Pop</option>
      <option value="jazz">Jazz</option>
      <option value="metal">Metal</option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      inputSearch: "",
    };
  },
};
</script>

<style lang="scss" scoped></style>

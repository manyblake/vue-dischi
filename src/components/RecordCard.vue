<template>
  <div class="card">
    <picture>
      <img :src="img" />
    </picture>
    <h3 class="title">
      {{ title }}
    </h3>
    <h4 class="author">
      {{ author }}
    </h4>
    <p class="year">
      {{ year }}
    </p>
  </div>
</template>

<script>
export default {
  props: {
    img: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss" scoped>
img {
  width: 100%;
  height: 100%;
}

.card {
  text-align: center;
  color: white;
  background-color: #2e3a46;
  padding: 1rem;
  min-height: 400px;

  picture {
    aspect-ratio: 1/1;
    width: 100%;
    display: block;
  }

  h3 {
    text-transform: uppercase;
    margin: 2rem auto;
  }

  h4,
  p {
    color: #777777;
  }
}
</style>

<template>
  <div class="container">
    <ul class="records-list">
      <li v-for="(record, i) in records" :key="i" class="record-card">
        <RecordCard
          :title="record.title"
          :img="record.poster"
          :author="record.author"
          :year="record.year"
        />
      </li>
    </ul>
  </div>
</template>

<script>
import RecordCard from "./RecordCard.vue";

export default {
  props: {
    records: Array,
  },
  components: {
    RecordCard,
  },
};
</script>

<style lang="scss" scoped>
.container {
  max-width: 1200px;
  margin: 0 auto;
}

ul {
  list-style-type: none;
}

.records-list {
  display: grid;
  grid-template-columns: repeat(5, minmax(0, 1fr));
  gap: 3rem;
}
</style>

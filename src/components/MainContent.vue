<template>
  <div class="container">
    <ul class="records-list">
      <li v-for="(record, i) in filteredRecords" :key="i" class="record-card">
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
import axios from "axios";

export default {
  data() {
    return {
      records: [],
    };
  },

  props: {
    genre: String,
    author: String,
  },

  computed: {
    filteredRecords() {
      if (this.genre && this.author) {
        return this.records
          .filter((record) => record.genre.toLowerCase() === this.genre)
          .filter(
            (record) =>
              record.author.toLowerCase().split(" ").join("") === this.author
          );
      } else if (this.genre) {
        return this.records.filter(
          (record) => record.genre.toLowerCase() === this.genre
        );
      } else if (this.author) {
        return this.records.filter(
          (record) =>
            record.author.toLowerCase().split(" ").join("") === this.author
        );
      }

      return this.records;
    },
  },

  components: {
    RecordCard,
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
  created() {
    this.getRecords();
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

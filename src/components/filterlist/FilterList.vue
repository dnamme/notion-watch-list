<template>
  <div id="wrapper">
    <h3>Filters</h3>

    <div id="status-tags-wrapper">
      <FilterTag v-for="tag in statuses" :key="tag" :text="tag" />
    </div>

    <div id="genre-tags-wrapper">
      <FilterTag v-for="tag in genres" :key="tag" :text="tag" />
    </div>
  </div>
</template>

<script>
import FilterTag from "./FilterTag.vue";

export default {
  name: "FilterList",
  components: {
    FilterTag,
  },
  props: {
    statuses: {
      default: () => [
        "Upcoming",
        "Not Started",
        "Watching",
        "Completed",
        "Renewed",
        "Dropped",
      ],
      type: Array,
    },
    genres: {
      default: () => [
        "Action",
        "Adventure",
        "Comedy",
        "Drama",
        "Horror",
        "Romance",
      ],
      type: Array,
    },
  },
};
</script>

<style scoped>
#wrapper {
  padding: 4rem 5rem 0 5rem;
}

h3 {
  margin: 0;

  color: white;
}

#status-tags-wrapper {
  display: flex;
  flex-flow: row;
  flex-wrap: wrap;

  margin-top: 24px;
}

#genre-tags-wrapper {
  display: flex;
  flex-flow: row;
  flex-wrap: wrap;

  margin-top: 16px;
}
</style>

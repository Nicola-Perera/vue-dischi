<template>
  <div id="filterBox">
    <select
    name="genre_filter"
    id="genre_filter"
    v-model='filterGenre'
    @change="$emit('search-genre', filterGenre)">
      <option value="all">all</option>
      <option value="rock">rock</option>
      <option value="pop">pop</option>
      <option value="jazz">jazz</option>
      <option value="metal">metal</option>
    </select>
  </div>
</template>

<script>
export default {
  data() {
    return {
      filterGenre: '',
    };
  },
};
</script>

<style lang="scss">
</style>

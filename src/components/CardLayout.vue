<template>
  <div id="CardLayout">
    <filterBox />
    <div class="poster">
      <img :src="poster" alt="" />
    </div>

    <h2>{{ title }}</h2>
    <h3>{{ author }}</h3>
    <h3>{{ year }}</h3>
  </div>
</template>

<script>
import filterBox from './Filter.vue';

export default {
  name: 'CardLayout',
  components: {
    filterBox,
  },
  props: {
    poster: String,
    title: String,
    author: String,
    year: String,
  },
};
</script>

<style lang="scss">
</style>

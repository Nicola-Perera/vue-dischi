<template>
  <div id="app">
    <SiteHeader />
    <SiteMain />
  </div>
</template>

<script>
import SiteHeader from './components/SiteHeader.vue';
import SiteMain from './components/SiteMain.vue';

export default {
  name: 'App',
  components: {
    SiteHeader,
    SiteMain,
  },
};
</script>

<style lang="scss">
// reset rules
    * {
        box-sizing: border-box;
        margin: 0;
        padding: 0;
    }
#app {
  .brend_light_grey {
    background-color: #2E3A46;
  }
  #SiteMain {
    background-color: #1E2D3B;
    .card {
      margin: 1rem 0;
    }
  }
}
</style>

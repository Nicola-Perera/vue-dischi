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
  .songs_library {
    padding: 3rem 0 20rem;
    display: flex;
    flex-wrap: wrap;
    justify-content: center;
    justify-content: space-around;
  }

  // header & cards color
  .brend_light_grey {
    background-color: #2E3A46;
  }
  #SiteMain {

    // library color
    background-color: #1E2D3B;

    // single card settings
    .card {
      margin: .6rem .5rem;
      width: calc(100% / 7);
      text-align: center;
      padding: 1rem;

      // song cover
      .poster {
        width: 100%;
        margin: auto;
        img {
         width: 100%;
        }
      }

      // song title
      h2 {
        color: white;
        margin: .5rem 0;
      }

      // song author and year
      h3 {
        color: #808080;
      }
    }
  }
}
</style>

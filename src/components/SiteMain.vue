<template>
    <div id='SiteMain'>
        <div class="tracks_library" v-for="song in response" :key="song.title">

        </div>
    </div>
</template>

<script>
// import CardLayout from './components/CardLayout.vue';

export default {
  name: 'SiteMain',
  components: {
    //   CardLayout,
  },
};
</script>

<style lang="scss">

</style>

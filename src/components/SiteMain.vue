<template>
  <div id="SiteMain">
    <div class="songs_library" v-if="!loading">
      <CardLayout
        v-for="song in songs"
        class="card brend_light_grey"
        :poster="song.poster"
        :title="song.title"
        :author="song.author"
        :year="song.year"
        :key="song.title"
      />
    </div>

    <!-- loading screen -->
    <div class="loading" v-else>
      <h1>Loading...</h1>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardLayout from './CardLayout.vue';

export default {
  name: 'SiteMain',
  components: {
    CardLayout,
  },
  data() {
    return {
      songs: [],
      loading: true,
      error: '',
    };
  },

  mounted() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((Response) => {
        console.log(Response.data);
        this.songs = Response.data.response;
        this.loading = false;
      })
      .catch((Error) => {
        console.log(Error, 'ERRORE!');
        this.error = `ERRORE ${Error}`;
      });
  },
};
</script>

<style lang='scss'>
</style>

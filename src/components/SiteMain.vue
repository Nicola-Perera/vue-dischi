<template>
  <div id="SiteMain">
    <div class="songs_library" v-if="!loading">
      <CardLayout
        v-for="song in response"
        class="card brend_light_grey"
        :poster="song.poster"
        :title="song.title"
        :author="song.author"
        :year="song.year"
        :key="song.title"
      />
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

  methods: {
    callApi() {
      axios
        .get('https://flynn.boolean.careers/exercises/api/array/music')
        .then((Response) => {
          console.log(Response.data);
          this.songs = Response.data;
          this.loading = false;
        })
        .catch((Error) => {
          console.log(Error, 'ERRORE!');
          this.error = `ERRORE ${Error}`;
        });
    },
  },
};
</script>

<style lang='scss'>
</style>

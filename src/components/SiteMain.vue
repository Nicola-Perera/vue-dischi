<template>
  <div id="SiteMain">
    <filterBox @search-genre='search' :songs='songs'/>
    <div class="songs_library" v-if="!loading">
      <CardLayout
        v-for="song in getGenreFilter"
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
      <h1>Loading library...</h1>
    </div>
  </div>
</template>

<script>
import axios from 'axios';
import CardLayout from './CardLayout.vue';
import filterBox from './Filter.vue';

export default {
  name: 'SiteMain',
  components: {
    CardLayout,
    filterBox,
  },
  data() {
    return {
      songs: [],
      loading: true,
      error: '',
      searchGenre: '',
    };
  },

  mounted() {
    axios
      .get('https://flynn.boolean.careers/exercises/api/array/music')
      .then((Response) => {
        this.songs = Response.data.response;
        this.loading = false;
      })
      .catch((Error) => {
        console.log(Error, 'ERRORE!');
        this.error = `ERRORE ${Error}`;
      });
  },
  methods: {
    search(text) {
      this.searchGenre = text;
    },
  },
  computed: {
    getGenreFilter() {
      if (this.searchGenre === 'all') {
        console.log(this.songs);
        return this.songs;
      }
      const filtered = this.songs.filter((song) => song.genre.includes(this.searchGenre));
      return filtered;
    },
  },
};
</script>

<style lang='scss'>
h1 {
  color: greenyellow;
}
</style>

<template>
  <div id="app">
    <SearchBar  @searching="startSearch" />

    <Content :movies="movieList" />
  </div>
</template>

<script>
import Content from './components/Content.vue'
import SearchBar from './components/SearchBar.vue'
import axios from 'axios';

export default {
  name: 'App',
  components: {
    Content,
    SearchBar
  },
  data() {
    return {
       apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=971c983e8762f921083518b235cba01b&query=",
        movieList: [],
        searchMovie: "",
    }
  },
  methods: {
    getMovies() {
      axios 
      .get(this.apiUrl+this.searchMovie)
      .then((result) => {
          this.movieList = result.data.results
      })
    },
    startSearch(filmToSearch) {
      this.searchMovie = filmToSearch;
      this.getMovies();
    }
  }
}
</script>

<style lang="scss">
*{
  margin: 0;
  padding: 0;
  box-sizing: border-box;
}
</style>

<template>
  <div id="app">
    <SearchBar :films="filmList" @search="startSearch" />

    <Content :selectedMovie="filmToSearch" @filmReady="getfilmList" />
  </div>
</template>

<script>
import Content from './components/Content.vue'
import SearchBar from './components/SearchBar.vue'


export default {
  name: 'App',
  components: {
    Content,
    SearchBar
  },
  data() {
    return {
      filmList: [],
      filmToSearch: "",
    }
  },
  methods: {
    getfilmList(allFilms) {
      this.filmList = allFilms;
    },
    startSearch(filmToSearch) {
      this.filmToSearch = filmToSearch;
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

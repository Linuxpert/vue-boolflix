<template>
  <div id="backgoundFilms">
      <div id="container">
          <Film 
            v-for="movie, i in filteredMovie" 
            :key="i"
            :details="movie" />
      </div>
  </div>
</template>

<script>
import axios from "axios";
import Film from '@/components/Film.vue';

export default {
  name: 'Content',
    components: {
        Film,
    },
    props:{
        selectedMovie: String
    },
    data() {
        return  {
            apiUrl: "https://api.themoviedb.org/3/search/movie?api_key=971c983e8762f921083518b235cba01b&query="+ this.searchMovie,
            movieList: [],
            searchMovie: "",

        }
    },
    created(){
        this.getMovies();
    },
    computed: {
        filteredMovie(){
          if(this.selectedMovie === ''){
              return 
          }

          return this.movieList.filter((item) => {
              return item.title.toLowerCase().includes(this.selectedMovie)
          })
      }
    },
    methods: {
        getMovies() {
            axios 
            .get(this.apiUrl)
            .then((result) => {
                this.movieList = result.data.results
            })
        },

        
    }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #backgoundFilms{
        background-color: grey;
        height: 100vh;
        #container{
            width: 60%;
            margin: 0 auto;
            display: flex;
            flex-wrap: wrap;
            justify-content: space-evenly;
        }
    }
</style>

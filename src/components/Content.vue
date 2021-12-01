<template>
  <div id="backgoundFilms">
      <div id="container">
          <Film 
            v-for="movie, i in movies" 
            :key="i"
            :details="movie" />
      </div>
  </div>
</template>

<script>
import Film from '@/components/Film.vue';

export default {
  name: 'Content',
components: {
    Film,
},
props:{
    movies: Array
},
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

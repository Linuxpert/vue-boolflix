<template>
  <div id="backgoundFilms">
      <div class="container">
          <Film 
            v-for="movie, i in movies" 
            :key="i"
            :film="movie" />
      </div>
      <div class="container">
          <Series
            v-for="tv, i in tvs" 
            :key="i"
            :serie="tv" />
      </div>
  </div>
</template>

<script>
import Film from '@/components/Film.vue';
import Series from '@/components/Series.vue';

export default {
  name: 'Content',
components: {
    Film,
    Series
},
props:{
    movies: Array,
    tvs: Array
},

}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    
    .container{
        width: 60%;
        margin: 20px auto;
        display: flex;
        flex-wrap: wrap;
        justify-content: space-evenly;
    }

</style>

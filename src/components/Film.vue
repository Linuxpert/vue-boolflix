<template>
  <div class="film">
    <div class="img_poster">
      <img :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" alt="">
    </div>
    <div class="info">
      <h3>{{film.title}}</h3>
    </div>
    <div class="info">
      <h3>{{film.original_title}}</h3>
    </div>
    <div class="info">
      <img v-if="film.original_language === 'en'" src="https://lonampio.files.wordpress.com/2014/08/bandiera-inglese.png?w=256" :alt="film.title" class="flag">
      <img v-else-if="film.original_language === 'it'" src="https://www.uniba.it/english-version/students/services/special-needs-sector/bandiera-italiana.png/image" :alt="film.title" class="flag">
      <img v-else-if="film.original_language === 'fr'" src="https://www.ristorantemarinadelnettuno.com/wp-content/uploads/2019/08/bandiera-francia-png-3.png" :alt="film.title" class="flag">
      <span v-else>language not found</span>
    </div>
    <div class="info">
      <h3>{{film.vote_average}}</h3>
    </div>
      
  </div>

  
</template>

<script>

export default {
  name: 'Film',
  props: {
    film: Object,
  },
  
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

      .film{
        background-color: honeydew;
        border: 1px solid black;
        width: 20%;
        .img_poster{
          img{
            width: 100%;
          }
          
        }
        .info{
          margin: 20px 0;
        }
        .flag{
          width: 50px;
          height: 50px;
        }
      }
    
</style>

<template>
  <div class="series">
      <div class="img_poster">
          <img v-if="serie.poster_path === null" src="https://www.losbagliato.it/wp-content/uploads/2021/07/copertina-netflix-23-giugno-960x960.png" alt="" class="img_null">
          <img v-else :src="`https://image.tmdb.org/t/p/w342${serie.poster_path}`" alt="">
          
          <div class="info">
                <h3>Titolo: {{serie.name}}</h3>
                <h3>Titolo originale: {{serie.original_name}}</h3>

                <img v-if="serie.original_language === 'en'" src="https://lonampio.files.wordpress.com/2014/08/bandiera-inglese.png?w=256" :alt="serie.title" class="flag">
                <img v-else-if="serie.original_language === 'it'" src="https://www.uniba.it/english-version/students/services/special-needs-sector/bandiera-italiana.png/image" :alt="serie.title" class="flag">
                <img v-else-if="serie.original_language === 'fr'" src="https://www.ristorantemarinadelnettuno.com/wp-content/uploads/2019/08/bandiera-francia-png-3.png" :alt="serie.title" class="flag">
                <h3>Voto: <star-rating :rating="getStar()" :star-size="30" :increment="1" :show-rating="false"></star-rating></h3>
                <h3>Overview: {{serie.overview}}</h3>

          </div>
            
      </div>

      
  </div>

  
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
  name: 'Series',
  components: {
    StarRating
  },
  props: {
    serie: Object,
  },
  methods: {
    getStar(){
      return this.film.vote_average / 2
    }
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

      .series{
        background-color: honeydew;
        border: 1px solid black;
        width: 20%;
        .info{
            h3{
                margin-bottom: 30px;
            }
        }
      }
      .img_null{
        object-fit: cover;
        width: 100%;
        height: 100%;
      }

    
</style>

<template>
  <div class="film">
    <div class="img_poster">
      <img :src="`https://image.tmdb.org/t/p/w342${film.poster_path}`" alt="" class="img_film">
      <div class="info">
        <div class="info_film">
          <h3>Titolo:</h3><span>{{film.title}}</span>
        </div>
        
      
        <div class="info_film">
          <h3>Titolo originale: </h3><span>{{film.original_title}}</span>
        </div>
        
      
        <div class="info_film lingua">
          <h3>Lingua:</h3><img v-if="film.original_language === 'en'" src="https://lonampio.files.wordpress.com/2014/08/bandiera-inglese.png?w=256" :alt="film.title" class="flag">
           <img v-else-if="film.original_language === 'it'" src="https://www.uniba.it/english-version/students/services/special-needs-sector/bandiera-italiana.png/image" :alt="film.title" class="flag">
           <img v-else-if="film.original_language === 'fr'" src="https://www.ristorantemarinadelnettuno.com/wp-content/uploads/2019/08/bandiera-francia-png-3.png" :alt="film.title" class="flag">
           <span v-else>language not found</span>
        </div>
        
      
        <div class="info_film">
          <h3>Voto: </h3><star-rating :rating="getStar()" star-size="30" increment="1" :show-rating="false"></star-rating>
        </div>
        <div class="info_film">
          <h3>Overview: </h3><span>{{film.overview}}</span>
        </div>
        
      </div>
    </div>
      
  </div>

  
</template>

<script>
import StarRating from 'vue-star-rating'

export default {
  name: 'Film',
  components: {
    StarRating
  },
  props: {
    film: Object,
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

      .film{
        background-color: #000;
        border: 1px solid black;
        width: 24%;
        margin: .5%;
        position: relative;
        cursor: pointer;
        .flag{
          width: 50px;
          height: 50px;
        }
        .info_film h3{
          display: inline;
          color: red;
        }
        .info_film.lingua{
          display: flex;
          align-items: center;
          img{
            margin-left: 10px;
          }
        }
        
      }
      .film:hover .img_film{
          display: none;
        }

        .img_poster .img_film{
          width: 100%;
          height: 500px;
          display: block;
        }

        .info{
          display: none;
          position: absolute;
          top: 5px;
          left: 5px;
          margin: 20px 0;
          color: #fff;
        }

        .film:hover .info{
          display: block;
        }
    
</style>

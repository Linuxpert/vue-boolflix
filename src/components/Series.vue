<template>
  <div class="series">
      <h3>{{serie.name}}</h3>
      <h3>{{serie.original_name}}</h3>
      <h3>{{serie.original_language}}</h3>
      <h3>{{serie.vote_average}}</h3>
  </div>

  
</template>

<script>

export default {
  name: 'Series',
  props: {
    serie: Object,
  },
  methods: {
    getImgLanguage(element){
        if(element.original_language === 'en'){
            return ""
        }else if (element.original_language === 'it'){
            return "https://banner2.cleanpng.com/20171217/580/italia-flag-png-5a37458281e1f0.924151041513571714532.jpg"
        }else if (element.original_language === 'ja'){
            return ""
        }else if (element.original_language === 'tl'){
            return ""
        }else if (element.original_language === 'fr'){
            return ""
        } else {
            return "no found"
        }
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

      }
    
</style>

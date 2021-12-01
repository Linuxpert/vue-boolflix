<template>
  <div class="film">
      <h3>{{details.title}}</h3>
      <h3>{{details.original_title}}</h3>
      <h3>{{details.original_language}}</h3>
      <h3>{{details.vote_average}}</h3>
  </div>

  
</template>

<script>

export default {
  name: 'Content',
  props: {
    details: Object,
  }
}

</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">

      .film{
        background-color: honeydew;
        border: 1px solid black;
        width: 20%;

      }
    
</style>

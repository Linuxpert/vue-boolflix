<template>
  <div class="series">
      <h3>{{details.name}}</h3>
      <h3>{{details.original_name}}</h3>
      <h3>{{details.original_language}}</h3>
      <h3>{{details.vote_average}}</h3>
  </div>

  
</template>

<script>

export default {
  name: 'Series',
  props: {
    details: Object,
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

<template>
  <div id="search-bar">
      <h1>
          BOOLFLIX
      </h1>
      <div id="search-box">
          <form action="">
              <input type="text"  v-model="inputText"  placeholder="Inserisci il titolo del film" >
              <button @click.prevent="$emit('searching', inputText)">Search</button>
          </form>
          
      </div>
  </div>
</template>

<script>
export default {
  name: 'SearchBar',
    data() {
        return {
            inputText: ""
        }
    },
}
</script>

<!-- Add "scoped" attribute to limit CSS to this component only -->
<style scoped lang="scss">
    #search-bar {
        height: 100px;
        background-color: #000;
        display: flex;
        align-items: center;
        justify-content: space-between;
        h1{
            color: red;
            margin: 10px;
        }
        #search-box{
            margin: 20px;
        }

    }
</style>

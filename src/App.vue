<template>
  <div id="app">
    <!-- <userName /> -->
    <rickAndMortyAPI />
  </div>
</template>

<script>
import rickAndMortyAPI from './components/rickAndMortyAPI.vue';
// import userName from './components/userName.vue'
export default {
  name: 'App',
  components: {
    // userName,
    rickAndMortyAPI
  }
}
</script>

<style scoped>
#app {
  background-color: gray;
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  margin: 0;
  overflow: hidden;
  padding-bottom: 60px;
}
</style>

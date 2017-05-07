<template>
  <div id="app">
    <h3>{{title}}</h3>
    <Character v-for="(id, index) in initial_ids" :id="id" key="index"/>
  </div>
</template>

<script>
import Character from './components/Character.vue'
export default {
  name: 'app',
  data() {
    return {
      title: 'Generate Your Team',
      initial_ids: Array.apply(null, Array(15)).map(function (_, i) {return i+1;}),
    }
  },
  components: {
    Character,
  },
}
</script>

<style type="text/css">
body{
  background-color: #262328;
}
#app{
  font-family: 'Avenir', Helvetica;
  -webkit-font-smooting: antialiased;
  -moz-osx-font-smooting: grayscale;
  text-align: center;
  margin-top: 2rem;
  color: #fff;
}
</style>

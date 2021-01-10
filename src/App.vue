<template>
  <div id="app">
    <MoxiangMovie />
  </div>
</template>

<script>
import MoxiangMovie from './components/moxiangMovie.vue'

export default {
  name: 'app',
  components: {
    MoxiangMovie
  }
}
</script>

<style>
#app {
  font-family: 'Avenir', Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

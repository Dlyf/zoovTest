<template>
  <div id="app">
    <Zoov msg="Welcome to Your Vue.js App"/>
    <ZoovMap />
  </div>
</template>

<script>
import Zoov from './components/Zoov.vue'
import ZoovMap from './components/ZoovMap.vue'

export default {
  name: 'App',
  components: {
    Zoov,
    ZoovMap
  }
}
</script>

<style>
#app {
  font-family: Avenir, Helvetica, Arial, sans-serif;
  -webkit-font-smoothing: antialiased;
  -moz-osx-font-smoothing: grayscale;
  text-align: center;
  color: #2c3e50;
  margin-top: 60px;
}
</style>

<template>
  <div id="app">
    <HelloWorld msg="Welcome to Your Vue.js App"/>
    <Bier bier-text="Reinheitsgebot - Bier Parent"/>
  </div>
</template>

<script>
import HelloWorld from './components/HelloWorld.vue'
import Bier from './components/Bier.vue'

export default {
  name: 'App',
  components: {
    HelloWorld,
    Bier,
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

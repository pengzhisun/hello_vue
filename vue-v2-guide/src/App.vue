<template>
  <div id="app">
    <Introduction />
  </div>
</template>

<script>
import Introduction from './components/Introduction.vue'

export default {
  name: 'app',
  components: {
    Introduction
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

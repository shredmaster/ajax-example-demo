<template>
  <div id="app">
    <img alt="Vue logo" src="./assets/logo.png">
    <feel-lucky msg="How can I help you?"/>
  </div>
</template>

<script>
import FeelLucky from './components/FeelLucky.vue'

export default {
  name: 'app',
  components: {
      FeelLucky
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

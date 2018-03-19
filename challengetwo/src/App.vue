<template>
  <div id="app">
    <string></string>
    <email></email>
  </div>
</template>

<script>
import String from './components/string'
import Email from './components/email'
export default {
  name: 'App',
  components:{
    String,
    Email        
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

<template>
  <div id="app">
    <div class="container">
        <app-form  v-bind:formData="formData"></app-form>
    </div>
  </div>
</template>

<script>
import FormDynamic from './components/FormDynamic'
import formData from './assets/sample.json'
export default {
  name: 'App',
  components:{
    'app-form':FormDynamic   
  },
  data(){
    return{
      formData
    }
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

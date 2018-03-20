<template>
  <div id="app">
    <dynamicForm>
      
    </dynamicForm>
  </div>
</template>

<script>
import DynamicForm from './components/dynamicForm'
import Email from './components/email'
export default {
  name: 'App',
  components:{
    DynamicForm,
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

<template>
<form>
    <div v-for="component in components" v-bind:key="component.id">
        <div v-if="component.component=='string'" v-bind:class="component.col" class="form-group">
            <label for="exampleFormControlInput1">{{component.label}}</label>
            <input type="text" class="form-control" id="exampleFormControlInput1" v-bind:value="component.value">
        </div>
        <div v-if="component.component=='email'" v-bind:class="component.col" class="form-group">
            <label for="exampleFormControlInput1">{{component.label}}</label>
            <input type="text" class="form-control" id="exampleFormControlInput1" v-bind:value="component.value">
        </div>
        <div v-if="component.component=='radio'" v-bind:class="component.col" class="form-group">
            <div v-for="option in component.options" v-bind:key="option.id" class="form-check">
                <input class="form-check-input" type="radio" name="exampleRadios">
                <label class="form-check-label" for="exampleRadios1">{{option.male}}</label>
            </div>
        </div>
    </div>
</form>
</template>
<script>

import components from '../assets/sample.json'

export default {
  name:'dynamicForm',
  data(){
      return {
          components
      }
  },
  methods : {
      firstNameCol(){
          var col = this.firstName.col;
          return "col-md-" + col;
      },
      lastNameCol(){
          var col = this.lastName.col;
          return "col-md-" + col;
      }
  }
}
</script>

<style scoped>

</style>


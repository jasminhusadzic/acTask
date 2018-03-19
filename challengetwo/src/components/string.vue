<template>
<div class="row">
    <div v-bind:class="firstNameCol()">
        <label>{{firstName.label}}</label>
        <input type="text" v-bind:value='firstName.value'>
    </div>
    <div v-bind:class="firstNameCol()">
        <label>{{lastName.label}}</label>
        <input type="text" v-bind:value='lastName.value'>
    </div>
</div>
</template>
<script>
export default {
  name:'string',
  data(){
      return{
        firstName:{
            "label": "First name",
            "name": "first_name",
            "value": null,
            "component": "string",
            "col": 6
        },
        lastName:{
            "label": "Last name",
            "name": "last_name",
            "value": null,
            "component": "string",
            "col": 6
        } 
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


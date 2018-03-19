<template>
<div class="row">
    <div v-bind:class="[firstName.col]">
        <label>{{firstName.label}}</label>
        <input type="text" v-bind:value='firstName.value'>
    </div>
    <div v-bind:class="[firstName.col]">
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
            "col": "col-md-6"
        },
        lastName:{
            "label": "Last name",
            "name": "last_name",
            "value": null,
            "component": "string",
            "col": "col-md-6"
        } 
    }
  }
}
</script>

<style scoped>

</style>


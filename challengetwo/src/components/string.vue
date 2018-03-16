<template>
    <div v-bind:class="[col]">
        <label>{{label}}</label>
        <input type="text" v-bind:value='value'>
    </div>
</template>
<script>
export default {
  name:'string',
  data(){
      return{
        "label": "First name",
        "name": "first_name",
        "value": null,
        "component": "string",
        "col": 6
    }
  }
}
</script>

<style scoped>

</style>


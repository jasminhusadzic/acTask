<template>
<div class="row">
    <div v-bind:class="emailCol()">
        <label>{{email.label}}</label>
        <input type="email" v-bind:value='email.value'>
    </div>
</div>
</template>
<script>
export default {
  name:'email',
  data(){
      return{
        email:{
            "label": "Email",
            "name": "email",
            "value": null,
            "component": "email",
            "col": 6
        }
    }
  },
  methods : {
      emailCol(){
          var col = this.email.col;
          return "col-md-" + col;
      }
  }
}
</script>

<style scoped>

</style>


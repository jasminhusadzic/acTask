<template>
<div class="row">
    <!-- String -->
    <div v-for="component in formData" v-bind:key="component.id" v-if="component.component=='string'" v-bind:id="component.name" class="form-group" v-bind:class="dynamicClass(component)">
    <label v-bind:for="component.name">{{component.label}}</label>
    <input type="text" v-bind:name="component.name" v-bind:id="component.name" class="form-control"  v-model="component.value">
    </div>  
</div>
</template>
<script>

export default {
    props:['formData'],
    name:'String',
    data(){
        return{
            
        }
    },
  methods: {
     dynamicClass(component){
        var data = component;
            for (var key in data){
                if(key === "col"){
                    return "col-md-" + data[key];
                }
            }   
        }
  }
}
</script>

<style scoped>

</style>


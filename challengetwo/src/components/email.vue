<template>
<div class="row">
    <!-- Email -->
    <div v-for="component in formData" v-bind:key="component.id" v-if="component.component=='email'" v-bind:id="component.name" class="form-group"  v-bind:class="dynamicClass(component)">
        <label v-bind:for="component.name">{{component.label}}</label>
        <input type="email" v-bind:name="component.name" v-bind:id="component.name" class="form-control"  v-model="component.value">
    </div> 
</div>
</template>
<script>

export default {
    props:['formData'],
    name:'Email',
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


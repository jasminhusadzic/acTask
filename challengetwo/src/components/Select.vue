<template>
<div class="row">
    <!-- Email -->
    <div v-for="component in formData" v-bind:key="component.id" v-if="component.component=='select'" class="form-group" v-bind:id="component.name"  v-bind:class="dynamicClass(component)">
        <label v-bind:for="component.name">{{component.label}}:</label><br>
        <select v-for="option in component.options" v-bind:key="option.id" v-bind:id="component.name" v-model="component.value">
            <option v-for="opt in option" v-bind:key="opt.id">{{opt}}</option>
        </select>
    </div> 
</div>
</template>
<script>

export default {
    props:['formData'],
    name:'SelectComp',
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


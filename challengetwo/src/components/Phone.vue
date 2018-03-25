<template>
<div class="row">
    <!-- Phone -->
    <div v-for="component in formData" v-bind:key="component.id" v-if="component.component=='phone'" v-bind:id="component.name" class="form-group"  v-bind:class="dynamicClass(component)">
        <label v-bind:for="component.name">{{component.label}}:</label>
        <div v-for="ext in component.options" v-bind:key="ext.id">
            <div v-for="key in ext" v-bind:key="key.id">
                <select v-for="state in key" v-bind:key="state.id" v-model="component.value.ext" >
                    <option v-for="val in state" v-bind:key="val.id">{{val}}</option>
                </select>
                <input type="text" v-bind:id="component.name" class="form-control" v-model="component.value.phone">
            </div>
        </div> 
    </div>
</div>
</template>
<script>

export default {
    props:['formData'],
    name:'Phone',
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


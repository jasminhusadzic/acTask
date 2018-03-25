<template>
<div class="row">
    <!-- String -->
    <div v-for="component in formData" v-bind:key="component.id" v-if="component.component=='radio'" v-bind:id="component.name" class="form-group" v-bind:class="dynamicClass(component)">
    <label class="form-check-label" v-bind:for="component.name">{{component.label}}</label>
        <div v-for="option in component.options" v-bind:key="option.id" class="form-check">
            <div v-for="(radio,key) in option" v-bind:key="radio.id"> 
                <input type="radio" v-bind:name="component.name" v-bind:id="key" :value="radio">
                <label v-bind:for="radio">{{radio}}</label>
            </div>
        </div>
    </div>  
</div>
</template>
<script>

export default {
    props:['formData'],
    name:'Radio',
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


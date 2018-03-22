<template>
    <form @submit.prevent="submitForm">
        <div v-for="component in components" v-bind:key="component.id" class="form-group">
            <!-- String -->
            <div v-if="component.component=='string'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}</label>
                <input type="text" v-bind:name="component.name" v-bind:id="component.name" class="form-control"  v-model="component.value">
            </div>
            <!-- Email -->
            <div v-else-if="component.component=='email'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}</label>
                <input type="email" v-bind:name="component.name" v-bind:id="component.name" class="form-control"  v-model="component.value">
            </div>
            <!-- Radio -->
            <div v-if="component.component=='radio'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label class="form-check-label" v-bind:for="component.name">{{component.label}}</label>
                <div v-for="option in component.options" v-bind:key="option.id" class="form-check">
                    <div v-for="radio in option" v-bind:key="radio.id"> 
                        <input type="radio" v-bind:name="component.name" v-bind:id="radio" v-bind:value="radio">
                        <label v-bind:for="radio">{{radio}}</label>
                    </div>
                </div>
            </div>
            <!-- Select -->
            <div v-if="component.component=='select'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}:</label><br>
                <select v-for="option in component.options" v-bind:key="option.id" v-bind:id="component.name" v-model="component.value">
                    <option v-for="opt in option" v-bind:key="opt.id">{{opt}}</option>
                </select>
            </div>
            <!-- Phone -->
            <div v-if="component.component=='phone'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
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
            <!-- Multi string -->
            <div v-if="component.component=='multi_string'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}:</label>
                <input type="text" v-bind:id="component.name" class="form-control" v-model="component.value">
            </div>
        </div>
        <button type="submit">Submit</button>
        
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
      dynamicClass(component){
        var data = component;
            for (var key in data){
                if(key === "col"){
                    return "col-md-" + data[key];
                }
            }   
        },
        submitForm(e){
            var results = e.target.elements;
            console.log(results);
            for (var i in results){
                console.log(results[i])
                if (results[i].value){
                console.log(results[i].value);
                }
            }    
        }
    }
}
</script>

<style scoped>

</style>


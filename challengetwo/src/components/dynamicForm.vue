<template>
    <form>
        <div v-for="component in components" v-bind:key="component.id">
            <!-- String -->
            <div v-if="component.component=='string'"  v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}</label>
                <input type="text" v-bind:id="component.name" class="form-control" v-bind:value="component.value">
            </div>
            <!-- Email -->
            <div v-if="component.component=='email'" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}</label>
                <input type="email" v-bind:id="component.name" class="form-control"  v-bind:value="component.value">
            </div>
            <!-- Radio -->
            <div v-if="component.component=='radio'" v-bind:id="component.name" v-bind:class="dynamicClass(component)">
                <label class="form-check-label" v-bind:for="component.name">{{component.label}}</label>
                <div v-for="option in component.options" v-bind:key="option.id" class="form-check">
                    <div v-for="radio in option" v-bind:key="radio.id"> 
                        <input type="radio" v-bind:name="component.name" v-bind:id="radio">
                        <label v-bind:for="radio">{{radio}}</label>
                    </div>
                </div>
            </div>
            <!-- Select -->
            <div v-if="component.component=='select'" v-bind:class="dynamicClass(component)">
                <label v-bind:for="component.name">{{component.label}}:</label><br>
                <select v-for="option in component.options" v-bind:key="option.id" v-bind:id="component.name">
                    <option v-for="opt in option" v-bind:key="opt.id">{{opt}}</option>
                </select>
            </div>
            <!-- Phone -->
            <div v-if="component.component=='phone'" v-bind:class="dynamicClass(component)">
                <div>test</div>
            </div>
            <!-- Multi string -->
            <div v-if="component.component=='multi_string'" v-bind:class="dynamicClass(component)">
                <div>test2</div>
            </div>
        </div>
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
        }
    }
}
</script>

<style scoped>

</style>


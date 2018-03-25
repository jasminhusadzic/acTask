<template>
    <form @submit.prevent="submitForm">
        <app-string v-bind:formData="formData"></app-string>
        <app-email v-bind:formData="formData"></app-email>
        <app-radio v-bind:formData="formData"></app-radio>
        <app-select v-bind:formData="formData"></app-select>
        <app-phone v-bind:formData="formData"></app-phone>
        <app-multi-string v-bind:formData="formData"></app-multi-string>
        <button type="submit">Submit</button>
    </form>
</template>
<script>

import StringComp from './String'
import Email from './Email'
import Radio from './Radio'
import SelectComp from './Select'
import Phone from './Phone'
import MultiString from './MultiString'

export default {
    props:['formData'],
    name:'formDynamic',
    components:{
    'app-string': StringComp,
    'app-email':Email,
    'app-radio':Radio,
    'app-select':SelectComp,
    'app-phone':Phone,
    'app-multi-string':MultiString
  },
  data(){
      return {  
      }
  },
  methods:{
      submitForm(e){
         console.log(e);
            var data = e.target;
            for (var i=0; i<data.length-1;i++){
               if (data[i].value){
                
                    console.log(data[i].value);   
                }else{
                    console.log('Sva polja moraju biti upisana');break;
                }
            }   
        }
  }
}
</script>

<style scoped>

</style>


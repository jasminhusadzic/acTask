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

            var data = e.target;
            var results = [];   
            var json = [];
            var counter = 0;
            for (var i=0; i<data.length-1;i++){
                if(!data[i].value && data[i].type !=='radio') {
                    alert('Please insert all data');break;
                }
                else if (data[i].value && data[i].type !=='radio'){
                   results.push(data[i].value);  
                }else if(data[i].checked){
                    results.push(data[i].value);
                    counter++;
                }
            }
            for(var i=0; i < results.length;i++){
                json.push({
                    "first_name": results[0],
                    "last_name": results[1],
                    "email":results[2] ,
                    "gender": results[3],
                    "source_of_attention":results[4],
                    "phone": {
                        "ext": results[5],
                        "phone": results[6], 
                        },
                    "vouchers": [
                    results[7],
                    ]
                         });
                if( counter == 0){
                     alert('Please insert all data');
                     json = [];
                }else{
                    console.log(json); // Output
                }break;
            }
        }
    }
}
</script>

<style scoped>

</style>


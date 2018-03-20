<template>
<div class="row">
    <div v-if="component.component=='email'" v-bind:class="component.col" class="form-group">
        <label for="exampleFormControlInput1">{{component.label}}</label>
        <input type="text" class="form-control" id="exampleFormControlInput1" v-bind:value="component.value">
    </div>
</div>
</template>
<script>
export default {
  name:'email'
}
</script>

<style scoped>

</style>


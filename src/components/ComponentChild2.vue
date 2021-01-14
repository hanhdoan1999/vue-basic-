<template lang="">
    <el-card class="w-6/12"  >
     <h2 class="font-medium">Component Child 2</h2>
         <textarea cols="60" type="text" :value="ComponentChildValue" @input="(event)=>$emit('input',event.target.value)"></textarea>      
    </el-card>
</template>
<script>
export default {
  props: ["ComponentChildValue"],
  model:{
    prop:"ComponentChildValue",
    value:"input"
  }
};
</script>
<style lang="">
</style>
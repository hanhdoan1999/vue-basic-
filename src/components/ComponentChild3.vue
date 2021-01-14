<template lang="">
    <el-card class="w-6/12"  >
     <h2 class="font-medium">Component Child 3</h2>
         <textarea cols="60" type="text" :value="ComponentChildValue" @input="(event)=>$emit('update:ComponentChildValue',event.target.value)"></textarea>      
    </el-card>
</template>
<script>
export default {
  props: ["ComponentChildValue"],
};
</script>
<style lang="">
</style>